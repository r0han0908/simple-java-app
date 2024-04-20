pipeline{
  agent {label 'Jenkins-Agent '}
  tools {
    jdk 'Jav17'
    maven 'Maven'
  }
  stages{
    stage ("Clean Workspace"){
      steps {
        cleanWs()
      }
    }

    stage("checkout from SCM") {
      steps {
        git branch: 'main' , credentials : 'github', url: 'https://github.com/r0han0908/simple-java-app'
      }
    }

    stage("Build Application") {
      steps {
        sh "mvn clean package"
         }
      }

    stage("Test Application"{
      steps {
        sh "mvn test"
      }
    }
    
   }
} 
