pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                 echo 'hello, Cosmi!'
            }
            
            post {
                success {
                    // Trigger a deployment in Jira when the build succeeds
                    jiraSendDeploymentInfo(
                        idOrKey: 'TES-7',
                        versionName: '1.0',
                        environment: 'Production',
                        comment: 'Deployment succeeded'
                    )
                }
                
                failure {
                    // Trigger a deployment failure in Jira when the build fails
                    jiraSendDeploymentInfo(
                        idOrKey: 'TES-7',
                        versionName: '1.0',
                        environment: 'Production',
                        comment: 'Deployment failed'
                    )
                }
            }
        }
    }
}
