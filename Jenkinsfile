pipeline {
     agent any
     stages {
          stage("Download Image from Dockerhub") {
               steps {
                    sh "docker pull anirudhbly/anirudh_tomcat:8"
               }
          }
            
    
stage("Stop current running Docker containers and delete them") {
     steps {
      
          sh "docker stop \$(docker ps -qa)"
          sh "docker rm \$(docker ps -qa)"
     }
}

stage("Deploy to stagin") {
     steps {
          
          sh "docker run -d -it -v /var/lib/jenkins/workspace/Demo_Docker/target/:/usr/local/tomcat/webapps/ -p 8090:8080 --name Testtomcat anirudh_tomcat"
     }
}
          
     }
  post {
     always {
          sh "echo 'I did It'"
     }
}
}
