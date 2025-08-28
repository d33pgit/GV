pipeline {
    agent any
    
    parameters {
        string(name: 'BUILD_INPUT', defaultValue: '', description: 'Enter the build number/input for deploy test')
    }
    
    stages {
        stage('Build') {
            when {
                branch 'development'
            }
            steps {
                echo "Running build on development branch"
                // Add your build commands here
            }
        }
        
        stage('Test Setup') {
            steps {
                echo "Running test setup on all branches"
                // Add your test setup commands here
            }
        }
        
        stage('Deploy Test') {
            steps {
                script {
                    if (!params.BUILD_INPUT) {
                        error("BUILD_INPUT parameter is required for deploy test stage.")
                    }
                    echo "Deploying test for build: ${params.BUILD_INPUT}"
                    // Add your deploy test commands here using BUILD_INPUT
                }
            }
        }
    }
}
