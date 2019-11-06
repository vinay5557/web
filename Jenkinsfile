node {
    def app
    stage('clone repository') {
        git url:'https://github.com/vinay5557/web.git'
    }
    docker.build('vinay555/web1').inside("--volume=/var/run/docker.sock:/var/run/docker.sock") {  
   // The build here
}
    stage('Build Image') {
        app=docker.build("vinay555/web1:${env.BUILD_NUMBER}")
        
    }
    stage('Test Image') {
        app.inside {
            echo 'Test passed'

        }
    }
    stage('Push Image') {
        docker.withRegistry('https://registry.hub.docker.com','dockerhub')
        app.push("${env.BUILD_NUMBER}")
    }
    
}
