pipeline {

    agent any
    
    environment {
        NEW_VERSION = "1.3.0"
    }

    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    
    stages {

    stage("init"){
            steps{
              script {
                gv = load "build-script.groovy"
              }

           }
    }
    
    stage("build"){
            steps {
              script {
                gv.buildApp()
              }
            }
       }
        
    stage("test"){
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
              script {
                gv.testApp()
              }
            }
        }
        
    stage("deploy"){
            steps {
              script {
                gv.deployApp()
              }
            }
        }
    }
}
