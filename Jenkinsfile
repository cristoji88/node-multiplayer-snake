node ('Ubuntu-app-agent'){  
    def app
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       checkout scm
    }  
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line */
        app = docker.build("506sec/snake")
    }
    stage('Post-to-dockerhub') {
    
     docker.withRegistry('https://registry.hub.docker.com', '2dd34d5e-adb4-4552-b360-d9fecd35a925') {
            app.push("latest")
        			           }
         }
    stage('Pull-image-server') {
             
         sh "docker-compose down"
         sh "docker-compose up -d"	
      }
 
}
