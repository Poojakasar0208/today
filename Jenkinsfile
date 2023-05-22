pipeline {

         agent {
        
     label {
     
             label "built-in"
       customWorkspace "/mnt/game-of-life"
           }
    }
     tools {
             maven "maven-3.9.2"
            }
     
         stages {
   
          stage ("Delete Workspace Before Build") {
       
       steps {
            sh "rm -rf *"
          }
         }
       
        stage ("checkout SCM") {
       
       steps {
            git "https://github.com/Poojakasar0208/game-of-life.git"
          }
        }
  
           stage ("Build-stage") {
       
       steps {
            sh "mvn clean install -DskipTests=true"
            sh "cp -r /mnt/game-of-life/gameoflife-web/target/gameoflife.war /mnt/servers/apache-tomcat-9.0.74/webapps"
          }
    }

         }
         
}

