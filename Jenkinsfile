pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
               echo 'Hi, this is Pranita a Devops Engineer'
                        echo 'We are Starting the Testing' 
            }
            post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('Create Tomcat Docker Image'){
            steps {
                sh "pwd"
                sh "ls -a"
                sh "docker build . -t tomcatsamplewebapp:${env.BUILD_ID}"
            }
        }

    }
}
