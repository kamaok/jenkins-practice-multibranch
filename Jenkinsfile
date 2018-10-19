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
        git(url: 'git@github.com:kamaok/course.git', branch: 'test', credentialsId: 'jenkins-user-ssh-key')
      }
*/


    stage ('Deploy') {
      steps {
        sh 'mvn deploy'
        }
      }

    stage ('Sonar analysis') {
      steps {
        withSonarQubeEnv('my-sonarqube-demo') {
        sh 'mvn sonar:sonar'
          }
        }
      }


  }
}
