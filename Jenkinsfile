pipeline{
    agent{
        label 'k8s-node'
    }
    stages{
     /* stage('login'){
         steps{
            script{
            withCredentials([usernamePassword(credentialsId: 'docker_vm_maha_user', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')]) {
        // some block
        // With the help of this block, ,the slave will be connecting to docker-vm and execute the commands to create the containers.
        //sshpass -p ssh -o StrictHostKeyChecking=no user@host command_to_run
        //sh "sshpass -p ${PASSWORD} -v ssh -o StrictHostKeyChecking=no ${USERNAME}@${docker_server_ip} hostname -i"             }
        }
       }*/
       stage('dockerimagebuild'){
          steps{
            script{
                withCredentials([usernamePassword(credentialsId: 'docker_vm_maha_user', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')])  
                sh "sshpass -p ${PASSWORD} -v ssh -o StrictHostKeyChecking=no ${USERNAME}@${docker_server_ip} hostname -i"             
                sh "docker build -t node-app-i27 ."
            }
          }
       }
       stage('dockercontainerbuild'){
           steps{
            script{
                sh "docker run -dit -p 3003:3000 node-app-i27"
            }

           }
        }
    }
}