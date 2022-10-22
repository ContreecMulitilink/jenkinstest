pipeline {
    agent any
    tools {
        maven "maven3.8.6"
    }
    environment {
        ENGINEER = "olu"
        GITCRED = credentials('github_cred')
    }
    withCredentials([usernamePassword(credentialsId: 'github_cred', passwordVariable: 'GITPWD', usernameVariable: 'GITUSER')]) {
    // some block
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
                sh 'echo my git username is $GITCRED_USR'
                sh 'echo my git pwd is $GITCRED_PSW'
            }
        }
    }
}
