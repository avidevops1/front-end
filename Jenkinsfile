 pipeline {

  agent {
   dokcer {
     image 'node:4-alpine'
   }
   
  }
   
      stages{
        stage('build'){
            steps{
                echo 'this is the build job'
                sh 'npm install'
            }
        }
        stage('test'){
            steps{
                echo 'this is the test job'
                sh 'npm test'
                sleep 5
            }
        }
        stage('package'){
            steps{
                echo 'this is the package job'
                sh 'npm run package'
                archiveArtifacts '**/distribution/*.zip
            }
        }
    }
    
    post{
        always{
            echo 'this pipeline has completed...'
        }
        
    }
    
}

