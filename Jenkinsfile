pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'master', url: 'https://github.com/manjukolkar/bluestacks.git'
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
