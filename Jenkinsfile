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
            when {
                expression {
                    // Check if branch name contains "devops"
                    return env.BRANCH_NAME =~ /devops/
                }
            }
            steps {
                script {
                    // Extract environment name from branch name
                    def environment = env.BRANCH_NAME =~ /devops-(\w+)/
                    if (environment) {
                        echo "Deploying to ${environment[0][1]} environment"
                        // Add your deployment steps here
                    }
                }
            }
        }
    }
}
