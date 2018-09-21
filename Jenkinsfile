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
 

  stages {

/*    stage('Checkout') {
      steps {
        git(url: 'git@github.com:kamaok/course.git', branch: 'master', credentialsId: 'jenkins-user-ssh-key')
        }
      }
*/
    

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

/*    stage ('Sonar analysis') {
      steps {
        withSonarQubeEnv('my-sonarqube-demo') {
        sh 'mvn sonar:sonar'
          }
        }
      }
*/

  }
}
