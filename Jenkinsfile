pipeline {
 agent any
   stages {
     stage ('Checkout Stage') {
       steps {
           git changelog: false, poll: false, url: 'https://github.com/brad-jivedh/simple-java-project.git'
       }
     }
        stage ('Buil stage') {
          steps {
              sh 'mvn clean install'
       }
     }
        stage ('Push') {
          steps {
            echo "This is the push stage"
            }
     }
        stage ('Deploy') {
          steps {
            sh 'sudo rsync /var/lib/jenkins/workspace/tomcat/target/*.war ubuntu@15.206.79.202:/opt/apache-tomcat-9.0.87/webapps/'       }
     }
   }
}
