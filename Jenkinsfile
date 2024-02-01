pipeline { 

agent any 
environment {
        VERSION = '1.2.0'
        X = '10'
	}

stages {

  stage('git checkout') {
    steps {
       
      git credentialsId: 'Gihub-login', url: 'https://github.com/saikrishna21297/maven-webapp-project-1.git'
    
  }
  }
  stage('using envs') {
      steps {
          echo "the version is ${VERSION}"
          echo "The Value of X is ${X}"
      }
  }
  stage('validate') {
    steps {
      sh 'mvn validate'
    }
  }
  stage('compile') {
  steps {
   sh 'mvn compile'
  }
  }
  stage('package') {
    steps {
      sh 'mvn package'
    }
  }
  stage('clean WS') {
	      	steps {
			      cleanWs()
		       }
      	}
 
  
}
 
}
