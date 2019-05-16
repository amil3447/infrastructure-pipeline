node('linux'){
    stage('Test'){
        git credentialsId: '572fb6c3-7114-4509-9c68-26dd11305cf8', url: 'https://github.com/amil3447/infrastructure-pipeline.git/'
        sh 'cat README.md'
    }
    
    stage('aws'){
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '4745c8b8-b723-4ae9-bb9b-da9c97005878', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
           // some block
           sh 'aws cloudformation describe-stack-resources --stack-name jenkins --region us-east-1'   
        }
    }
}
