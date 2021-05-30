pipeline {
     agent any

     stages {
         stage ('Compile Stage') {
             steps {
                 withMaven (maven : 'Maven-3.8.1') {
                     sh 'mvn clean compile'
                 }
             }
                
         }
     }

     stages {
         stage ('Testing Stage') {
             steps {
                 withMaven (maven : 'Maven-3.8.1') {
                     sh 'mvn verify -Ddriver=chrome'
                 }
             }
                
         }
     }

     stages {
         stage ('Deployment Stage') {
             steps {
                 withMaven (maven : 'Maven-3.8.1') {
                     sh 'mvn serenity:aggregate'
                 }
             }
                
         }
     }

}