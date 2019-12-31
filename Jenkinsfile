pipeline {
    agent any
  //  tools {
      // Install the Maven version configured as "M3" and add it to the path.
     // maven "M3"
   //}
   options { 
      skipDefaultCheckout() 
  }
    stages {
        stage ('Compile Stage') {

            steps {
               
                    sh 'mvn clean compile'
               
            }
        }
        stage ('Testing Stage') {

            steps {
            
                    sh 'mvn test'
                
            }
        }
        stage ('Install Stage') {
            steps {
               
                    sh 'mvn install'
            }
        }
        stage ('Email'){
        steps{
         emailext (to: 'othmane.devlopix@gmail.com', replyTo: 'othmane.devlopix@gmail.com', 
         subject: "Email Report from - '${env.JOB_NAME}' ", 
         body: readFile("target/surefire-reports/TEST-ma.gr.sample_project.AppTest.xml"), 
         mimeType: 'text/html');
    }
    }
        
    }
}