node{
    def app

    stage('Clone') {
        checkout scm
    }
     stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    stage ('Build image') {
        app = docker.build("my_appp")
    }

    stage ('Run image') {
        docker.image('my_appp').withRun('-p 3000:3000 -m') { c -> sh 'docker ps'}
    }
}
