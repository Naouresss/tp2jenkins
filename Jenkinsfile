pipeline {
    agent any 
    tools { 
        maven 'maven'
    }
    stages {
        stage ("Clean up"){
            steps {
                deleteDir()
            }
        }
        stage ("Clone repo"){
            steps {
                sh "git clone https://github.com/Naouresss/tp2jenkins.git"
            }
        }
        stage ("Generate backend image") {
              steps {
                   dir("tp2jenkins"){
                      sh "mvn clean install"
                      sh "docker build -t docexp1-spring ."
                  }                
              }
          }
        stage ("Run docker compose") {
            steps {
                 dir("tp2jenkins"){
                    
                    sh " docker-ompose up -d"
                }                
            }
        }
     
    }
}
