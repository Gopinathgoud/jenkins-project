pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
  
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing.........'

            }
        }
        
        // Stage3: Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/DevopsLab-0.0.14-SNAPSHOT.war', type: 'war']], credentialsId: '09d3d0aa-003a-4cd4-8501-0561cffde4e3', groupId: 'com.devopslab', nexusUrl: '3.93.165.146:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'gopi', version: '0.0.14-SNAPSHOT'            }
        }

       // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' Deploying......'

            }
        }


//stages
    }

}
