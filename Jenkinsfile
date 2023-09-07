pipeline
{
  agent any

  tools {
    // Install the Maven version "M3" and add to the path
    maven "Maven 3"
  }

  stages {
    stage('Build') {
      steps
          // Get some code from a GitHub repository
          git 'https://github.com/vinodrathod07/git_session_281022.git'
         // Run Maven on a Unix agent.
         //sh "mvn -Dmaven.test.failure.ignore=true clean package"
 
      // To run Maven on a Windows agent
      bat "mvn -Dmaven.test.failure.ignore=true clean package"
  }
 
    post {
 
        // Record the test results
    success {
         junit '**/target/surefire-reports/TEST-*.xml'
        //Archive the jar
       archiveArtifacts 'target/*.jar'
        }
      }
    }
  }
}
         
