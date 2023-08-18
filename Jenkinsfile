pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("Test"){
            steps{
                bat "mvn test"
            }
           
        }
        stage("build"){
            steps{
                bat 'mvn clean package'
            }
        }
        stage("deploy"){
            steps{ echo '786'

            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
