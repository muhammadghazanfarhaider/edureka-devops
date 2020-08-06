pipeline
{
    agent any
    stages
    {
        stage('Checkout')
        {
            steps
            {
                git 'https://github.com/muhammadghazanfarhaider/edureka-devops.git'
            }
        }
        stage('Compile')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn compile'
            }
        }
        stage('Test')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn test'
            }
        }
        stage('Package')
        {
            steps
            {
                sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn package'
            }
        }
        stage('Deployment')
        {
            steps
            {
                sh 'sudo cp /var/lib/jenkins/workspace/AddressBookPipeline/target/addressbook.war /usr/share/tomcat/webapps && sudo systemctl stop tomcat && sudo rm -rf /usr/share/tomcat/webapps/addressbook && sudo systemctl start tomcat'
            }
        }
    }
}

