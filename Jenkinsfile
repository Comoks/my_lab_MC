node{
    def registryProjet='772552573479.dkr.ecr.eu-west-3.amazonaws.com/my_appp'
    def IMAGE="${registryProjet}:version-${env.BUILD_ID}"

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
                sh 'aws ecr get-login --no-include-email --region eu-west-3 | docker login -u AWS -p 772552573479.dkr.ecr.eu-west-3.amazonaws.com'
                sh 'docker push 772552573479.dkr.ecr.eu-west-3.amazonaws.com/my_appp:latest'
        }
      
        
    }

}
