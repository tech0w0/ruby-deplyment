pipeline {
    agent any

    parameters {
       choice(name: 'TARGET_ENV', choices: ['staging', 'production'], description: 'Please choose an environment')
    }

    stages {
       stage('Copy artifact') {
          steps {
             copyArtifacts filter: 'main.rb', fingerprintArtifacts: true, projectName: 'simple-ruby', selector: lastSuccessful()
          }
       }
    }
 }
