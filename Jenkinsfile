pipeline {
    agent any

    stages {
        stage('Install Apache2 and Deploy HTML') {
            steps {
                sh '''
                    # Update and install Apache2
                    sudo apt update
                    sudo apt install apache2 -y

                    # Start and enable Apache
                    sudo systemctl start apache2
                    sudo systemctl enable apache2

                    # Copy your HTML file to Apache's root
                    echo "<html><body><h1>Deployed from Jenkins</h1></body></html>" > calculator.html
                    sudo cp calculator.html /var/www/html/

                    # Set permissions
                    sudo chmod 644 /var/www/html/calculator.html
                '''
            }
        }

        stage('Verify') {
            steps {
                echo 'Access the site via http://<your-ip>/calculator.html'
            }
        }
    }
}

