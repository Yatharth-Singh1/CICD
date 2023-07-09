pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo building...'
		sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
stage('Build Yolo5 app') {
   steps {
       sh '''
            aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 854171615125.dkr.ecr.eu-north-1.amazonaws.comdocker
 	    build -t yathcicdtry .
	    docker tag yathcicdtry:latest 854171615125.dkr.ecr.eu-north-1.amazonaws.com/yathcicdtry:latest
            docker push 854171615125.dkr.ecr.eu-north-1.amazonaws.com/yathcicdtry:latest
       '''
   }
}
}