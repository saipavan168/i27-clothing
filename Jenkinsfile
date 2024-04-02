pipeline{
    agent{
        label 'k8s-node'
    }
    stages{
       stage('dockerimagebuild'){
          steps{
            script{
                sh "docker build -t node-app-i27
            }
          }
       }
       stage('dockercontainerbuild'){
           steps{
            script{
                sh "docker run -dit -p 3001:3000 node-app-i27
            }

           }
        }
    }
}