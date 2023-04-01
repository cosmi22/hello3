pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                jiraComment body: 'This comment was sent from Jenkins pipeline', issueKey: 'TES-7'
            }
        }
    }
}