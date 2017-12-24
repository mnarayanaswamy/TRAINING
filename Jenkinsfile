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
  }
}
