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
            fileParameter("/var/jenkins_home/workspace/JenkinsDeployServerPrivateKey.pem", "")
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
            sh "cd .."
            sh "pwd"
            sh "ls -lha"
        }
    }   
}
