node {
    stage('git checkout') {
    git 'https://github.com/AnupamaSoma/maven-project.git'
}
   stage('Build') {
    sh 'mvn install'
}
   stage('Deployment')
   {
       deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.82.183:8080')], contextPath: 'qaapp', war: '**\\*.war'
   }
   stage('testing')
    {
        git 'https://github.com/AnupamaSoma/FunctionalTesting.git'
        sh 'java -jar /var/lib/jenkins/workspace/scripted_pipeline/testing.jar'
    }
    stage('Delivery')
    {
        deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.83.134:8080')], contextPath: 'prodapp', war: '**\\*.war'
    }
    
}
