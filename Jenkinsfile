pipeline{
  
  agent{
   label "master" 
    
  }
  
  stages{
    stage("maven build and deploy"){
      steps{
        
       sh(script:'mvn deploy -s settings.xml -f trucks/pom.xml')
   
      }
    }    
  }
}
