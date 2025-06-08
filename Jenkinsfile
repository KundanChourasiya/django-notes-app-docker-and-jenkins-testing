@Library("shared-libraries") _
pipeline {
    agent {label 'vinod'}

    stages {
        stage('hello'){
            steps{
                script{
                    hello()
                }
            }
        }
        
        stage('code') {
            steps{
                script{
                    colne_project("https://github.com/KundanChourasiya/django-notes-app-docker-and-jenkins-testing.git", "main")
                }
            }
        }
        
        stage('build') {
            steps{
                script{
                    docker_build("notes-app", "latest", "kundanchourasiya")
                }
            }
        }
        
        stage('Push the code') {
            steps{
                script{
                    docker_push("notes-app", "latest", "kundanchourasiya")
                }
            }
        }

        stage('Deploy') {
            steps{
               script{
                   docker_compose()
               }
            }
        }
    }
}
