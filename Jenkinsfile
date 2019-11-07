node {
    def app
    stage('clone repository') {
        git url:'https://github.com/vinay5557/web.git'
    }
    docker.build('vinay555/web1').inside("--volume=/var/run/docker.sock:/var/run/docker.sock") {  
   // The build here
}
    stage('Build Image') {
        sh 'docker build -t vinay555/web1'
    }
    stage('Test Image') {
        app.inside {
            echo 'Test passed'

        }
    }
    stage('Push Image') {
                sh 'docker build -t vinay555/web1'
    }
}
