  
pipeline {
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
    
      
  }
}
