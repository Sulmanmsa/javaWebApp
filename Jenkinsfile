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
            steps{ deploy adapters: [tomcat9(credentialsId: '2d6d8293-1867-4708-ac7f-c0a169e81d40', path: '', url: 'http://localhost:9494/')], contextPath: 'javaWebApp', war: '**/*.war'

            }
        }
         stage('Copy') {
            steps {
                // Copy the index.jsp file to the Tomcat webapps directory
                bat "copy C:\\Users\\BISMILLAH\\.jenkins\\workspace\\javaWebApp\\index.jsp C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0_Tomcat9_temp\\webapps\\javaWebApp\\index.jsp"
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
