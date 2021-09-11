node{
    def app

    stage('Clone') {
        checkout scm
    }

    stage ('Build image') {
        app = docker.build ("my_appp")
    }

    stage ('Run image') {
        docker.image('my_appp').withRun('-p 3000:3000 -m') { c -> sh 'docker ps'}
    }
}
