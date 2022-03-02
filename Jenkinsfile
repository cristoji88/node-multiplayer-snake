node ('Ubuntu-app-agent'){  
   // def app
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       checkout scm
    }  
    stage('SAST'){
        sh 'echo SAST'
        /*build 'SECURITY-SAST-SNYK'*/
    }

    
    stage('Build-and-Tag') {
    sh 'echo Built and Tag'
        /* This builds the actual image; synonymous to
         * docker build on the command line */
      //  app = docker.build("amrit96/snake")
    }
    stage('Post-to-dockerhub') {
    sh 'echo PostDockerhub'
    /* docker.withRegistry('https://registry.hub.docker.com', 'training_creds') {
            app.push("latest")
        			}*/
         }
    stage('SECURITY-IMAGE-SCANNER'){
       sh 'echo ContainerSec'
        /* build 'SECURITY-IMAGE-SCANNER-AQUAMICROSCANNER'*/
    }
  
    
    stage('Pull-image-server') {
    sh 'echo Pull-imager-server'
        /* sh "docker-compose down"
         sh "docker-compose up -d"*/	
      }
    
    stage('DAST')
    sh 'echo DAST'   
    /* {
        build 'SECURITY-DAST-OWASP_ZAP'
        }
 
}
