pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/project"
        }
    }

    stages {
        stage('one') {
            steps {
                sh 'yum install docker -y'
                sh 'service docker start'
                sh 'docker run -dp 80:80 --name webserver2 httpd'
                sh 'cd /mnt/project'
                sh 'rm -rf index.html'
                sh 'docker cp index.html webserver2:/usr/local/apache2/htdocs'
            }
        }
    }
}
