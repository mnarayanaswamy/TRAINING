pipeline{
  
  agent{
   label "PROD" 
    
  }
  
  stages{
    stage("maven build and deploy"){
      steps{
        
       sh(script:'mvn deploy -X -s settings.xml -f pom.xml')
   
      }
    }   
    
   stage("Build docker image tag and push"){
    
    steps{
    sh "docker login -u mnarayan -p madhu@123"
    sh "docker build --tag tomcat ."
    sh "docker tag tomcat mnarayanaswamy/webapp:${BUILD_NUMBER}"
    sh "docker push mnarayanaswamy/webapp:${BUILD_NUMBER}"
    
       }
     }

  }
}
