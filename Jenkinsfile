pipeline{
    agent{
        label 'k8s-node'
    }
    stages{
       stage('copydockerfile'){
        steps{
            script{
                sh "cp /.cicd/Dockerfile /home/raksharoshni/jenkis/workspace/i27-clothing_master/"
            }
        }
       }
       stage('dockerimagebuild'){
          steps{
            script{
                sh "docker build -t node-app-i27 ."
            }
          }
       }
       stage('dockercontainerbuild'){
           steps{
            script{
                sh "docker run -dit -p 3001:3000 node-app-i27"
            }

           }
        }
    }
}