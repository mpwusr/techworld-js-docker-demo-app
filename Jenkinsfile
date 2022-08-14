pipeline {

    agent any
    
    stages {
        stage("build"){
            steps {
                echo 'building the application...'
            }
        }
        
    stage("test"){
            steps {
                echo 'testing the application...'
            }
        }
        
    stage("deploy"){
            steps {
                echo 'deploying the application...'
            }
        }
    }
    post {
        always {
          // 
          steps {
            echo 'always step'
          }
        }
        success {
          //
          steps {
            echo 'success step'
          }
        }
        failure {
          //
          steps {
            echo 'failure step'
          }
        }
    }
}
