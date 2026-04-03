# Apne local computer me repo clone kar
git clone https://github.com/shirsatgaurav/cd.git
cd cd

# Jenkinsfile bana
cat > Jenkinsfile << 'EOF'
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Building on branch: ${env.BRANCH_NAME}"
                sh 'echo "Build completed"'
            }
        }
        
        stage('Test') {
            steps {
                echo "Testing application..."
                sh 'echo "Tests passed"'
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        echo "🚀 Deploying to DEV environment"
                    }
                    else if (env.BRANCH_NAME == 'stage') {
                        echo "🚀 Deploying to STAGE environment"
                    }
                    else if (env.BRANCH_NAME == 'main') {
                        input "⚠️ Deploy to PRODUCTION?"
                        echo "🚀 Deploying to PRODUCTION"
                    }
                }
            }
        }
    }
    
    post {
        success {
            echo "✅ Pipeline SUCCESS for ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ Pipeline FAILED for ${env.BRANCH_NAME}"
        }
    }
}
EOF
