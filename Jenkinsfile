pipeline {
  agent any

  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3')
    disableConcurrentBuilds()
  }

/*   triggers {
     bitbucketPush()
  }
*/
   tools {
    maven 'maven-demo'
  }
 

/*  stages {

    stage('Checkout') {
      steps {
        git(url: 'git@github.com:kamaok/course.git', branch: 'test', credentialsId: 'jenkins-user-ssh-key')
        }
*/      }

    

    stage ('Compile') {
      steps {
        sh 'mvn clean compile'
        }
      }

    stage ('Test') {
      steps {
        sh 'mvn test'
        }
      }

    stage ('Deploy') {
      steps {
        sh 'mvn deploy'
        }
      }

<<<<<<< HEAD
     stage ('Sonar analysis') {
=======
    stage ('Sonar analysis') {
>>>>>>> test
      steps {
        withSonarQubeEnv('my-sonarqube-demo') {
        sh 'mvn sonar:sonar'
          }
        }
      }


  }
}
