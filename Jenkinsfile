node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t leonardom/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push leonardom/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f leonardom/laravel:$BUILD_NUMBER'
    }
}
