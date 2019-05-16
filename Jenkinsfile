node('linux'){
    stage('Test'){
        git url: 'https://github.com/amil3447/infrastructure-pipeline.git/'
        sh 'cat README.md'
    }
    
    stage('aws'){
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '4745c8b8-b723-4ae9-bb9b-da9c97005878', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
           // some block
           sh 'aws cloudformation describe-stack-resources --stack-name infrastructure-pipeline --region us-east-1'   
        }
    }
}
