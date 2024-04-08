pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/lavanya1330/maven.git'
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
            deploy adapters: [tomcat9(credentialsId: '7461fe0e-0ff9-4ec7-8eff-3e433f40fd1d', path: '', url: 'http://172.31.94.45:8080')], contextPath: 'Testapp', war: '**/*.war'
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                git 'https://github.com/lavanya1330/functionaltesting.git'
        
                sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline/testing.jar'
            }
        }
       
    }
}
