pipeline {
    agent any
    stages {
        stage('拉取代码') {
            steps {
                git url: 'https://github.com/sustech-cs304/Teedy.git'
            }
        }
        stage('编译') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('单元测试') {
            steps {
                sh 'mvn test'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}