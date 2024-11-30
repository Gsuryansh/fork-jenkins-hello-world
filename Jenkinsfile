pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M399"
    }

    stages {
        stage('Echo Version'){
            steps{
                sh 'echo Print maven version'
                sh 'mvn -version'
            }
            
        }
        stage('Build'){
            steps{
                // Get some code from git hub repo
                // git branch: 'main', credentialsId: '245ec485-bd7b-49c9-af22-69000a80cd8a', poll: false, url: 'https://github.com/Gsuryansh/fork-jenkins-hello-world.git'
                
                // Run maven package CMD
                sh 'mvn clean package -Dskiptests=true'
        }
        }
        stage('Unit Tests'){
            steps{
                script{
                    for (int i = 0; i<60; i++){
                    echo "${i+1}"
                    sleep 1
                }
                }
                
                sh "mvn test"
            }
        }
    }
}
