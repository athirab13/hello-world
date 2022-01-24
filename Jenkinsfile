pipeline {
    agent none
    stages{
        stage('Run sequential stage and mvn build'){
            steps {
		sh 'cd hello-world'
		sh 'mvn clean install'
                echo "Sequential Stage 1"
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
