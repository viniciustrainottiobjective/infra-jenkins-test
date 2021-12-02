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
            fileParameter("/var/jenkins_home/workspace/Testing File Parameter/JenkinsDeployServerPrivateKey.pem", "")
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
