pipeline {
    agent any

    stages{
        stage("install dependencies"){
            steps{
                echo "========executing A Build========"
                sh "npm install"
            }
        }
        stage("Build the pipeline"){
            steps{
                echo "========executing A Build========"
                sh "npm run build"
                archiveArtifacts artifacts: 'build/**/*', fingerprint: true
            }
        }
        stage("Build Docker Image & Push"){
            steps{
              withCredentials([usernamePassword(credentialsId: 'docker-hub')]){  
                sh 'printenv'
                sh 'docker build -t oseghale1/tourApp:""$GIT_COMMIT"" .'
                sh 'docker push oseghale1/tourApp:""$GIT_COMMIT""'
            }  
        }
        }
    }
}