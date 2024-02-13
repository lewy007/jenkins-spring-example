pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
        jdk 'jdk-17'
    }

    stages {
        stage('Build') {
            steps {
                sh "mvn clean compile -Dmaven.compiler.source=17 -Dmaven.compiler.target=17"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test -Dmaven.compiler.source=17 -Dmaven.compiler.target=17"
            }
        }
        stage('Deploy') {
            steps {
                sh "mvn clean heroku:deploy -Dmaven.compiler.source=17 -Dmaven.compiler.target=17"
            }
        }
    }
}
