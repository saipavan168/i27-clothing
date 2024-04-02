pipeline{
    agent{
        label 'k8s-node'
    }
    environment{
        Image_Name= "node-app-i27"
     }
    stages{
       stage('dockerimagebuild'){
          steps{
            script{
                sh "docker build -t ${env.Image_Name}
            }
          }
       }
       stage('dockercontainerbuild'){
           steps{
            script{
                sh "docker run -dit -p 3001:3000 ${env.Image_Name}
            }

           }
        }
    }
}