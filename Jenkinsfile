node {
    withDockerContainer(args: '-v /root/.m2:/root/.m2', image: 'maven:3-alpine') {
        stage('Build') {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app']]])
            sh 'mvn clean package'
        }
        stage('Test') {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app']]])
            sh 'mvn test'
        }
    }
}