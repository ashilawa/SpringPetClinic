pipeline {
  agent {
    label 'master'
  }
  tools {
    maven 'M3'
  }
  stages {

    stage('checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/ashilawa/SpringPetClinic.git'
      }

    }

    stage('Build') {
      steps {
        bat 'mvn compile'
      }

    }

    stage('Test') {
      steps {
        bat 'mvn test'
      }

    }

    stage('Package') {
      steps {
        bat 'mvn package'
      }

    }

    stage('Deploy') {
      steps {
        bat "copy \\target\\spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar \"C:\\Users\\aramchan\\work\\spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar\""
        
        bat 'java -jar C:\\Users\\aramchan\\Jenkins\\.jenkins\\workspace\\JenkinsDeclarativePipelineDemo\\target\\spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar'
      }

    }

  }
}
