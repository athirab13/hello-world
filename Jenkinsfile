pipeline {
    agent none
    tools { 
        maven "maven3.8.4" 
        jdk "jdk8" 
    }
    stages{
	stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
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
