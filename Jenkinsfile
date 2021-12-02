#!groovy

def fileParameter(String name, String description) {
    return [
            $class      : 'FileParameterDefinition',
            name        : name,
            description : description
    ]
}

properties([disableConcurrentBuilds(),
    [$class: 'ParametersDefinitionProperty',
        parameterDefinitions: [
            fileParameter("JenkinsDeployServerPrivateKey.pem", "")
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
            sh "pwd"
        }
    }   
}
