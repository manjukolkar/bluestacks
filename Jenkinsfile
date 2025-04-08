pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'dev', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Install httpd') {
            steps {
                sh 'sudo yum install httpd -y'
            }
        }

        stage('Start and Enable httpd') {
            steps {
                sh '''
                    sudo systemctl enable httpd
                    sudo systemctl start httpd
                '''
            }
        }

        stage('Copy Files') {
            steps {
                sh 'sudo cp index.html /var/www/html/'
            }
        }
    }
}
