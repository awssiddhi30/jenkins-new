pipeline {
    agent none
    stages{
        stage('build'){
            agent{
                label 'agent-1'
            }
            steps{
                echo "this is build"
            }

        }
        stage('test'){
            steps{
                echo "this is test"
            }
        }
         stage('deploy'){
            steps{
                echo "this is deploy new update"
            }
        }
    }
}
