pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tompass', path: '', url: 'http://54.198.69.119:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
