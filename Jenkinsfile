node('maven_label') {
   def mvnHome
   stage('Preparation') { // for display purposes
      //git branch: '${branch}', url: 'https://github.com/jglick/simple-maven-project-with-tests.git'
      //git branch: '${branch}', url: 'https://github.com/sscotts2004/visacard.git'
      git 'https://github.com/sscotts2004/visacard.git'



               
      mvnHome = tool name: 'maven-3.6.0', type: 'maven'

   }
   stage('Build') { // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts  'target/*.jar'
   }
   
   stage('sayhello') {
      sayHello "Edureka"
      }
   
   
}   
