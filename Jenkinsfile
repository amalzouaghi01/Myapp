pipeline 
{
          agent any
            stages {
                stage('Pull') {
                     steps{
                        script{
                            checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                               userRemoteConfigs: [[
                                   credentialsId: '393dd3704a3046b7bb0db5551b2f8fc9',
                                   url: 'https://github.com/amalzouaghi01/Myapp.git']]])
                              }
                           }
                        }
                        stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
                        stage ('Build') {
	
		      steps {
			 script{
			
			    sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
	
			      }
			     }
	             }
                    }          
}

