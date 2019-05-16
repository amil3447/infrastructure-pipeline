node('linux'){
    stage('Test'){
        git url: 'https://github.com/amil3447/infrastructure-pipeline.git'
        sh 'cat README.md'
    }
    
    stage('aws'){
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '4745c8b8-b723-4ae9-bb9b-da9c97005878', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
           // some block
           sh "aws ec2 describe-instances --region us-east-1"  
           sh 'aws cloudformation describe-stack-resources --stack-name w11-hands-on --region us-east-1'
        }
    }
}
