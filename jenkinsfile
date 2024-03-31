pipeline {
    agent any

    parameters {
        choice(name: 'BUILD_ENV', choices: ['development', 'production'], description: 'Select environment to build')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy the application after build')
    }

    stages {
        stage('Build') {
            steps {
                echo "Building the project for ${params.BUILD_ENV} environment"
                // Add build commands here
            }
        }

        stage('Test') {
            steps {
                echo "Running tests"
                // Add test commands here
            }
        }

        stage('Deploy') {
            when {
                expression { params.DEPLOY == true }
            }
            steps {
                echo "Deploying the application to ${params.BUILD_ENV} environment"
                // Add deployment commands here
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully"
        }
        failure {
            echo "Pipeline failed"
        }
    }
}
