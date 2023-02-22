pipeline{
    agent any
    
    tools{
        nodejs "node"
    }
    stages{
        stage('Clone repository'){
          steps{
            git 'https://github.com/Metto01/gallery.git'
        }
    }
        stage('Build'){
          steps{
           sh 'npm install'
        }
    }
}
}