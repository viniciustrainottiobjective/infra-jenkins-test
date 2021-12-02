#!groovy

def fileParameter(String name, String description) {
    return [
            $class      : 'Base64FileParameterDefinition',
            name        : name,
            description : description
    ]
}

properties([disableConcurrentBuilds(),
    [$class: 'ParametersDefinitionProperty',
        parameterDefinitions: [
            fileParameter("Jenkins DeployServerPrivateSSHKey", "")
        ]
    ]
])

node ('master'){
    stage('Checkout') {
        checkout scm
    }

    stage('Testing') {
        script {
            sh "echo ${params.'Jenkins DeployServerPrivateSSHKey'}"
        }

        withFileParameter("Jenkins DeployServerPrivateSSHKey") {
            sh "cat '${params.'Jenkins DeployServerPrivateSSHKey'}'"
        }
    }   
}
