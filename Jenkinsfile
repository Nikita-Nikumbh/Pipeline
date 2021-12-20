// Declarative //
pipeline {
    agent any

    stages {
        stage('One') {
            steps {
                echo 'Hi, This is trinesis Technologies'
            }
        }
        stage('Two') {
            steps {
                echo 'Do you want to proceed??'
            }
        }
        stage('Three') {
            when {
                   not {
                         branch "main"
                       }
                 }        
            steps {
                echo "Hello"
            }
        }
        stage('Four') {
                        parallel {
                             stage('Unit Test') {
                                                steps {
                                                      echo "Running the unit test..."
                                                }
                                 }                     
                    stage('Integration Test') {
                                                agent {
                                                      docker {
                                                              reuseNode false
                                                              image 'ubuntu'
                                                      }
                                                }
                                                steps {
                                                      echo 'Running the integration test..'
                                                }  
                                     }                                    
                       }
              }
        }
    }


