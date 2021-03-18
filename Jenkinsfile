// docs: https://jenkins.io/doc/pipeline/steps/credentials-binding/


    stage('usernamePassword') {
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
  
