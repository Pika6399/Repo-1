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
                sh 'docker run -itdp 80:80 --name webserver1 httpd bash'
                sh 'cd /mnt/project'
                sh 'cp index.html webserver1:/usr/local/apache2/htdocs'
            }
        }
    }
}
