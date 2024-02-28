node {
    stage('git checkout') {
    git 'https://github.com/nksri2022/maven-project.git'
}
  stage("build") {  
           	    steps {  
                      echo " build successfully"  
                      sh "mvn clean package"
              	    }  
         	    } 
    stage('Deployment')
   {
       deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.12.69:8080')], contextPath: 'qaapp', war: '**\\*.war'
   }
