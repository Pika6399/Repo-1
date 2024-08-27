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
                sh 'docker run -itdp 80:80 --name webserver1 httpd bash'
                sh 'cd /'
                sh 'chmod 777 -R mnt'
                sh 'cd /mnt/project'
                sh 'docker cp index.html webserver1:/usr/local/apache2/htdocs'
            }
        }
    }
}
