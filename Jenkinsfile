pipeline {
  
  environment {
    tomcatWeb = 'C:\\Program Files\\Apache Software Foundation\\Tomcat 10.0\\webapps'
    tomcatBin = 'C:\\Program Files\\Apache Software Foundation\\Tomcat 10.0\\bin'
    tomcatStatus = ''
    
   }
  
  
  agent any 
  tools {
    maven 'MAVEN_HOME'
  }
  stages {
    stage ('Initialize') {
      steps {
        bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
    stage ('Build') {
      steps {
      bat 'mvn clean package'
       }
    }
    
    stage('Deploy to Tomcat'){
      steps {
     bat "copy target\\WebApp.war \"${tomcatWeb}\\WebApp.war\""

     }
   }
    
      
  }
}
