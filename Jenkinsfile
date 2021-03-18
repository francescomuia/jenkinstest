// docs: https://jenkins.io/doc/pipeline/steps/credentials-binding/

pipeline {
  agent any
  stages {
    stage("Checkout") { 
        steps{
        checkout([
         $class: 'GitSCM',
         branches: scm.branches,
         doGenerateSubmoduleConfigurations: scm.doGenerateSubmoduleConfigurations,
         extensions: scm.extensions,
         userRemoteConfigs: scm.userRemoteConfigs,
         credentialsId: 'sicve'
        }
    ])
    }

    stage('usernamePassword') {
      steps {
        script {
          withCredentials([
            usernamePassword(credentialsId: 'sicve',
              usernameVariable: 'username',
              passwordVariable: 'password')
          ]) {
            print 'username=' + username + 'password=' + password

            print 'username.collect { it }=' + username.collect { it }
            print 'password.collect { it }=' + password.collect { it }
          }
        }
      }
    }
  }
}