pipeline {
    agent any
    stages {
        stage('Dynamic Stages') {
            steps {
                script {
                    def branchName = env.BRANCH_NAME.toLowerCase()
                    if (branchName == 'develop') {
                        buildAndDeploy('dev')
                    } else if (branchName == 'staging') {
                        buildAndDeploy('stage')
                    } else if (branchName == 'production') {
                        buildAndDeploy('prod')
                    } else {
                        echo "No specific stages defined for branch ${branchName}"
                    }
                }
            }
        }
    }
}

def buildAndDeploy(branchType) {
    stage("${branchType}/${env.BRANCH_NAME}") {
        steps {
            sh "echo 'Start ${branchType.capitalize()} server deployment'"
            sh "mvn -Dmaven.test.failure.ignore=true clean package"
            // Add any additional build steps here
        }
    }

    stage("${branchType}/${env.BRANCH_NAME}/Deploy") {
        steps {
            // Add deployment steps here
            sh "echo 'Deploying ${branchType.capitalize()} server'"
        }
    }

    stage("${branchType}/${env.BRANCH_NAME}/Login to remote host") {
        steps {
            // Add login steps here
            sh "echo 'Logging in to remote host for ${branchType.capitalize()} server'"
        }
    }
}
