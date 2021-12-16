node {

    stage('Clone repository') {

        checkout scm
    }

    stage('Build image') {
        /* Referencing the image name in AWS */

        app = docker.build("underwater")
    }
    
    stage('Test image') {
    /* Empty for test purposes */

    }

    stage('Push image') {
        /* Referencing the AWS registry. Tagging with the Jenkins build number and the latest tag */
        docker.withRegistry('720766170633.dkr.ecr.us-east-2.amazonaws.com/octopus-underwater-app', 'ecr:us-east-2:AWS') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
   
} 


