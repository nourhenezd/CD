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
    stage ('Build') {
               steps{
                 script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml -u root --private-key=/var/lib/jenkins/.ssh/id_rsa"
                 }
               }

        }
        stage ('Dokcer build') {
               steps{
                 script{
                    sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml -u root --private-key=/var/lib/jenkins/.ssh/id_rsa"
                 }
               }

        }

        

    }
}

