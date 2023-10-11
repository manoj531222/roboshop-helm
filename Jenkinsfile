pipeline {

  agent any

  parameters {
    string(name: 'component', defaultValue: '', description: 'App Component Name')
    string(name: 'app_version', defaultValue: '', description: 'App_Version')
  }

  stages {

    stage('Clone App Repo') {
      steps {
        dir('APP') {
          git branch: 'main', url: 'https://github.com/manoj531222/${component}'
        }
      }

    }

    stage('Helm Deploy') {
      steps {
        sh 'helm upgrade -i ${component} . -f APP/values.yaml --set app_version=${app_version}'
      }
    }

  }

}