
pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Step 1: Developer code checkout from GitHub'
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Step 2: Compiling application source code - SIMULATED'
            }
        }

        stage('Unit Tests') {
            steps {
                echo 'Step 3: Executing developer unit tests - SIMULATED'
            }
        }

        stage('Build') {
            steps {
                echo 'Step 4: Packaging application artifact - SIMULATED'
            }
        }

        stage('Deploy to QE') {
            steps {
                echo 'Step 5: Deploying application to QE environment - SIMULATED'
            }
        }
        
stage('Trigger QE Smoke Tests') {
    steps {
        echo 'Triggering Selenium QE Automation Pipeline'

        build job: 'Selenium-Java-Pipeline',
              parameters: [
                  string(name: 'TEST_SUITE', value: 'smoke')
              ],
              wait: true,
              propagate: true
    }
}
        
    }

    post {
        success {
            echo 'Developer CI Pipeline completed successfully'
        }

        failure {
            echo 'Developer CI Pipeline failed'
        }
    }
}
