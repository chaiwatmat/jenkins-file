node ('master'){
    stage('Checkout'){
        git 'https://github.com/chaiwatmat/jenkins-file.git'
    }

    stage('Build'){
        echo 'build now'
    }

    stage('notify result'){
        emailext attachLog: true, 
            from: 'noreply@jenkins.com',
            body: 'Check console output at $BUILD_URL to view the results.', 
            subject: '$PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS!', 
            replyTo: 'noreply@jenkins.com', 
            to: 'chaiwat.mat.dev@gmail.com'
    }

    stage('finish'){
        cleanWs()
    }
}