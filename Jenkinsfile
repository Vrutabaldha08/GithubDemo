pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build Stage"
            }
        }
        stage('Test') {
            steps {
                echo "Test Stage"
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def environment = ""
                    if (env.BRANCH_NAME.contains("dev")) {
                        environment = "dev"
                    } else if (env.BRANCH_NAME.contains("prod")) {
                        environment = "prod"
                    } else if (env.BRANCH_NAME.contains("stage")) {
                        environment = "stage"
                    } else {
                        environment = "unknown"
                    }

                    echo "Deploying to ${environment} environment"
                    // Add your deployment steps here
                }
            }
        }
    }
}
