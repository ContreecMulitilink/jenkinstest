pipeline {
    agent any
    tools {
        maven "maven3.8.6"
    }
    environment {
        ENGINEER = "olu"
        GITCRED = credentials('github_cred')
    }
    options {
        timestamps()
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
                echo "my git username is ${env.GITCRED_USR}"
                echo "my git pwd is ${env.GITCRED_PSW}"
            }
        }
    }
}
