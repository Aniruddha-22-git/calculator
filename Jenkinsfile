pipeline {
    agent {
        label 'built-in'
    }
    environment {
        GIT_REPO = 'https://github.com/Aniruddha-22-git/calculator.git'
        CLONE_DIR = '/mnt/hello'
    }
    stages {
        stage('Prepare Workspace') {
            steps {
                sh '''
                sudo rm -rf ${CLONE_DIR}
                mkdir -p ${CLONE_DIR}
                '''
            }
        }
        stage('Clone Repository') {
            steps {
                dir("${CLONE_DIR}") {
                    sh '''
                    git clone ${GIT_REPO} .
                    '''
                }
            }
        }
        stage('Install Apache2') {
            steps {
                sh '''
                sudo apt update
                sudo apt install apache2 -y
                sudo systemctl enable apache2
                sudo systemctl start apache2
                '''
            }
        }
        stage('Deploy HTML to Apache') {
            steps {
                sh '''
                sudo cp ${CLONE_DIR}/calculator.html /var/www/html/
                sudo chmod 644 /var/www/html/calculator.html
                '''
            }
        }
    }
    post {
        success {
            echo "✅ HTML deployed! Access it at: http://<your-server-ip>/calculator.html"
        }
        failure {
            echo "❌ Deployment failed. Check logs."
        }
    }
}


