node("docker") {
    docker.withRegistry('venkatgude90/dokcer-test', 'DokcerHub') {
    
        git url: "https://github.com/venkatgude1230593/CI-with-Jenkins-in-AWS-Demo-1.git", credentialsId: '590049bc-03ad-42e2-9365-6d06cfe41284'
    
        sh "git rev-parse HEAD > .git/commit-id"
        def commit_id = readFile('.git/commit-id').trim()
        println commit_id
    
        stage "build"
        def app = docker.build "demo"
    
        stage "publish"
        app.push 'master'
        app.push "${commit_id}"
    }
}
