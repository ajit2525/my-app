node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
      // Get maven home path
      //def mvnHome =  tool name: 'Maven', type: 'maven'   
      sh "mvn package"
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      Ajit''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'ajiteee2394@gmail.com'
   }
   stage('SonarQube Analysis') {
        def mvnHome =  tool name: 'Maven', type: 'maven'
        withSonarQubeEnv('sonarqube') { 
          sh 'mvn sonar:sonar'
           
        }
   }
}


