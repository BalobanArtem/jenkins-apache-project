pipeline {
    agent any

    stages {
        stage('Install Apache') {
            steps {
                echo 'Installing Apache server...'
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y apache2'
            }
        }
        stage('Log Analysis') {
            steps {
                echo 'Checking for 4xx/5xx errors in logs...'
                // Смотрим последние 50 строк и ищем ошибки
                sh 'sudo tail -n 50 /var/log/apache2/access.log | grep -E " (4|5)[0-9]{2} " || echo "No errors found"'
            }
        }
    }
}
