pipeline {
    agent any

    stages {
        stage('Clone App Repo') {
            steps {
                dir('APP'){
                  git branch: 'main', url: 'https://github.com/manoj531222/cart'
                }
            }
        }
    }
    stages {
            stage('Helm Deploy') {
                steps {
                    sh 'helm upgrade -i ${component} . APP/values.yaml'
                }
            }
        }
}
