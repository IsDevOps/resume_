pipeline {
    agent any

    stages{
        stage("Build the pipeline"){
            steps{
                echo "========executing A Build========"
                sh "npm run build"
                archiveArtifacts artifacts: 'target/build.zip', fingerprint: true
            }
        }
    }
}