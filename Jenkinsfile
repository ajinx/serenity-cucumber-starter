pipeline {
     agent any

     tools {
        maven 'Maven-3.8.1'
    }

     stages {
         stage ('Compile Stage') {
             steps {
                     sh 'mvn clean compile'
                 }
             }
                
    
         stage ('Testing Stage') {
             steps {
                     sh 'mvn verify -Ddriver=chrome'
                 }
             }
        
     
         stage ('Deployment Stage') {
             steps {
                     sh 'mvn serenity:aggregate'
                 }
             }

             post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
                
    }
     
}