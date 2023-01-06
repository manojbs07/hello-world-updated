pipeline {
    agent none
       
       stages {
         stage('Build') {
            agent {label 'tomcat1'}
            steps {
               git branch: 'main',url:'https://github.com/manojbs07/hello-world-updated'
                sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline
               mvn clean install'''
            }
         }
         stage('Deploy') {
            agent {label 'tomcat1'}
            steps {
              
          sh '''cd /home/ec2-user/jenkins/workspace/agentpipeline/target
               sudo cp *.war /root/opt/apache-tomcat-10.0.27/webapps'''

            }
         }
        
        }
      
      }
