pipeline {
    agent any
    tools {
        maven "MAVEN"
    //    jdk "JDK"
    }
    stages {
        stage('Initialize'){
            steps{
                //echo "PATH = ${M2_HOME}/bin:${PATH}"
                //echo "M2_HOME = /opt/maven"
				//echo "M2_HOME =/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/MAVEN/bin"
            }
        }
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/demo-pieline-2") {
                sh 'mvn'
				sh 'mvn -B -DskipTests clean package'
                }
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}