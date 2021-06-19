pipeline {
  
  def tomcatWeb = 'C:\\"Program Files"\\"Apache Software Foundation"\\Tomcat 10.0\\webapps'
  def tomcatBin = 'C:\\"Program Files"\\"Apache Software Foundation"\\Tomcat 10.0\\bin'
  def tomcatStatus = ''
  
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
     bat "copy target\\JenkinsWar.war \"${tomcatWeb}\\JenkinsWar.war\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }
    
      
  }
}
