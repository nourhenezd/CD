pipeline {

    agent any


    stages {
       stage ('Pull') {
               steps{
                 script{
                     checkout([$class: 'GitSCM', branches: [[name: '*/main']],userRemoteConfigs: [[ credentialsId: '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',url :'https://github.com/nourhenezd/CD.git']]])                 
                 }

		}
        }
    }
}

