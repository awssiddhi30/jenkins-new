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
            agent{
                label 'agent-1'
            }
            steps{
                echo "this is test"
            }
        }
         stage('deploy'){
            agent{
                label 'agent-1'
            }
            steps{
                echo "this is deploy new update"
            }
        }
    }
}
