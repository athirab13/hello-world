pipeline {
    agent none
    tools { 
        maven 'maven3.8.4' 
        jdk 'jdk8' 
    }
    stages{
	stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        stage('Run sequential stage and mvn build'){
            steps {
		sh '''
			cd hello-world
			mvn clean install
                	echo "Sequential Stage 1"
		 '''
            }
        }
        stage('Run Parallel stages'){
        parallel {
            stage ('Parallel stage 1') {
                steps {
                    echo "Parallel stage 1"
                }
            }
            stage ('Parallel stage 2') {
                steps {
                    echo "Parallel stage 2"
                }
            }
            stage ('Parallel stage 3') {
                steps {
                    echo "Parallel stage 3"
                }
            }
        }
        }
    }
}
