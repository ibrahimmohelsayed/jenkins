pipeline {

        agent {

        label 'master'

           }

	options {
	
	  buildDiscarder (logRotator(numToKeepStr:'2',artifactNumToKeepStr: '1'))

          }

        stages {

        stage ('build'){

           steps {
                sh 'R CMD build .'

                 }

             }

         }

	post {

	    always {

		archiveArtifacts  artifacts: 'dist/*.tar.gz' , fingerprint: true

            }


        }   




  }