node {
    def app
    stage('clone repository') {
        git url:'https://github.com/vinay5557/web.git'
    }
    
    stage('Build Image') {
        sh 'docker build -t vinay555/web1 .'
    }
    
    stage('Push Image') {
                sh 'docker push vinay555/web1'
    }
}
