node {
    def app
    stage('clone repository') {
        git 'https://github.com/vinay5557/web.git'
    }
    stage('Build Image') {
        app=docker.build("vinay555/web1:${env.BUILD_NUMBER}")
        
    }
    stage('Test Image') {
        app.inside {
            sh "Test Passed"
        }
    }
    stage('Push Image') {
        docker.withRegistry('https://registry.hub.docker.com','dockerhub')
        app.push("${env.BUILD_NUMBER}")
    }
}
