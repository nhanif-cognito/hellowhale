podTemplate(label: 'docker-agent', containers: [
    containerTemplate(name: 'docker', image: 'docker', command: 'cat', ttyEnabled: true)
  ],
  volumes: [
    hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
  ]
  ) {
    node('docker-agent') {
      container('docker') {
          docker.withRegistry('https://registry.hub.docker.com','dockerhub'){
          //  def customImage = docker.build("hello-world:${env.BUILD_ID}")
          sh 'docker pull nhanif/hellowhale'
        //  sh 'docker tag nhanif/hellowhale:${env.BUILD_ID}'
       }
     }
        //stage('Check running containers') {
            //container('docker') {
                // example to show you can run docker commands when you mount the socket
              //  sh 'docker ps'
               // sh 'docker pull hello-world'
                // sh 'docker info'
              //  sh 'docker run hello-world'



    }
}
