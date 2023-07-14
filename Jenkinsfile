node {

  stage ('checkout'){
           git branch: 'main', credentialsId: 'git_creds', url: 'https://github.com/Anusha0503/tomcat10-jakartaee9.git'
 
         }

   stage ('build'){ 
        withMaven(globalMavenSettingsConfig: '', jdk: 'java', maven: 'maven', mavenSettingsConfig: '', traceability: true) {
    sh 'mvn clean package'
           }
   
   }
   stage ('deploy'){
        
           
     deploy adapters: [tomcat9(credentialsId: 'tomcatid', path: '', url: 'http://34.227.104.220:8081/')], contextPath: null, war: '**/*.war'
   }
}
