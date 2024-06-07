pipeline{
    agent{
        label "node"
    }
    
        stage("Build the pipeline"){
            steps{
                echo "========executing A========"
                sh "yarn build"
                archiveArtifacts artifacts: 'target/build.zip', fingerprint: true

            }
           
        }
    }
