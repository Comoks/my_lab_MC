node{
    def registryProjet='772552573479.dkr.ecr.eu-west-3.amazonaws.com/my_appp'
    def IMAGE="${registryProjet}:latest"

    //environment {
     //   registry = "772552573479.dkr.ecr.eu-west-3.amazonaws.com/my_appp"
   // }
    stage('Clone') {
        checkout scm
    }

    stage ('Build image') {
        app = docker.build ("$IMAGE", '.')
    }

    stage('Push') {
        script{
                sh 'aws ecr get-login-password --region eu-west-3 | docker login --username AWS --password-stdin 772552573479.dkr.ecr.eu-west-3.amazonaws.com'
                sh 'docker push 772552573479.dkr.ecr.eu-west-3.amazonaws.com/my_appp:latest'
        }
      
        
    }

}
