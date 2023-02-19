pipeline {
    agent any

    stages {
      stage('Fetch Code') {
        steps {
    	echo 'Fetching code from repo'
    	git branch: 'main', changelog: false, poll: false, url: 'https://github.com/Hydra002/HelloWorldSpringBoot.git'
        // sh 'git clone https://github.com/Hydra002/HelloWorldSpringBoot.git'
        }
      }
    
      stage('Build') {
        steps {
    	echo 'Building project'
        sh 'chmod 777 ./gradlew'
    	sh './gradlew build'
        }
      }
    
      stage('Archive Artiface') {
        steps {
    	archiveArtifacts artifacts: 'build/libs/*.jar', followSymlinks: false
        }
      }

    }
}
