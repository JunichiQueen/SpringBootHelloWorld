pipeline{
        agent any
        stages{
		stage('---setup---'){
                        steps{
                                sh "sudo rm -rf junichi@51.104.215.198:/var/lib/wildfly-10.1.0.Final/standalone/deployments/*"
                        }
                }
		stage('---clean---'){
                        steps{
                                sh "sudo mvn clean"
                        }
                }
                stage('--test--'){
                        steps{
                                sh "mvn test"
                        }
                }
                stage('--package--'){
                        steps{
                                sh "mvn package"
                        }
                }
		stage('--deploy--'){
                        steps{
                                sh "cd /"
				sh "pwd"
				sh "sudo scp /var/lib/jenkins/workspace/testpipeline/target/PharmacyAide.war junichi@51.104.215.198:/var/lib/wildfly-10.1.0.Final/standalone/deployments/"
                        }
                }
        }
}