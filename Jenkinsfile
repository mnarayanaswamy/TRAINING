pipeline{
  
  agent{
   label "master" 
    
  }
  
  stages{
    stage("maven build and deploy"){
      steps{
        
       sh(script:'mvn deploy -X -s settings.xml -f pom.xml')
   
      }
    }   
    
   stage("Build docker image tag and push"){
    
    steps{
    sh "docker login -u sumeshkanayi -p Sia123"
    sh "docker build --tag tomcat ."
    sh "docker tag tomcat sumeshkanayi/webapp:${BUILD_NUMBER}"
    sh "docker push sumeshkanayi/webapp:${BUILD_NUMBER}"
    
       }
     }

  }
}
