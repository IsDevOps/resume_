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
                echo "========executings A Build========"
                sh "npm run build"
                archiveArtifacts artifacts: 'build/**/*', fingerprint: true
            }
        }
        stage("Build Docker Images & Push"){
            steps{
              withDockerRegistry([credentialsId:'docker-hub', url: '']){  
                sh 'printenv'
                sh 'sudo docker build -t oseghale1/tour:""$GIT_COMMIT"" .'
                sh "sudo docker login -u oseghale1 -p O9o55779759@"
                sh 'sudo docker push oseghale1/tour:""$GIT_COMMIT""'
            }  
        }
        }
    }
}