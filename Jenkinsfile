pipeline {
    agent { label 'Jenkins-agent' }
    tools {
        jdk 'Java17'
        maven 'maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git url: 'https://github.com/achalbychana/register-app.git', branch: 'main', credentialsId: 'github'

                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

        }

        stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }

}
}
