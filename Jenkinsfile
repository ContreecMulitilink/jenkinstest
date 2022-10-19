pipeline {
    agent any
    tools {
        maven "maven3.8.6"
    }
    environment {
        ENGINEER = "segun"
    }
    stages {
        stage('Initialization') {
            when {
                expression {
                    env.ENGINEER == 'olu'
                }
            }
            options {
                timeout (time: 30, unit: 'SECONDS')
            }
            steps {
                echo "testing my pipeline with ${env.ENGINEER}"
                echo "my current build is ${env.BUILD_NUMBER}"
                input (message: "Please review code, then proceed", ok: "yes")
            }
        }
    }
}