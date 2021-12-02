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
            fileParameter("JenkinsDeployServerPrivateSSHKey", "")
        ]
    ]
])

node ('master'){
    stage('Checkout') {
        checkout scm
    }

    stage('Testing') {
        script {
            sh "ls -lha"
        }

        withFileParameter("JenkinsDeployServerPrivateSSHKey") {
            sh "cat '$JenkinsDeployServerPrivateSSHKey'"
        }
    }   
}
