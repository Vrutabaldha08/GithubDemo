pipeline {
    agent any

    stages {
        stage("Build ${env.BRANCH_NAME}") {
            steps {
                echo "Build Stage"
            }
        }
        stage("Test ${env.BRANCH_NAME}") {
            steps {
                echo "Test Stage"
            }
        }
        stage("Deploy ${env.BRANCH_NAME}") {
            steps {
                echo "Deploy Stage"
                // Add your deployment steps here
            }
        }
    }
}
