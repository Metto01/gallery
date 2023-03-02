pipeline{
    agent any
    
    tools{
        nodejs "node"}
    
    stages{
    stage("Start") {
            steps{
               echo 'Build is starting'
            }
        }
         stage("Clone repository") {
            steps{
                git 'https://github.com/Metto01/gallery.git'
            }
        }
         stage('Get latest commit') {
            steps {
                sh '''
                   export COMMIT=$(git log --oneline | awk '{print $1}' | head -n 1)
                   echo $COMMIT
                   '''
            }
        }
        stage('NPM Installation'){
            steps{
                git 'https://github.com/Metto01/gallery.git'
                sh 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                sh 'curl -X POST https://dashboard.render.com/web/srv-cfpl2cp4rebfdato7etg'
            }
        }
        stage('End') {
            steps {
                echo 'Build is finished'
            }
        }
    }
}