@Library('mylibrary')_
pipeline
{
    agent any 
    stages
    {
        stage('ContDownload_loans')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")

                }
            }
        }
        stage('ContBuild_loans')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()

                }
            }
        }
         
    }
}
