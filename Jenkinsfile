pipeline {
    agent any

    stages {
        stage('Artifact Registry Creation') {
            when {
                expression {
                    true
                }
            }
            steps {
                dir("ops/ArtifactRegistry/prod") {
                    sh 'terraform --version'
                    sh 'terraform init '
                    sh 'terraform plan '
                    //sh 'terraform apply -auto-approve'
                }
                /*withCredentials([[$class:'GCPCredentialsBinding', credentialsId:'TERRAFORM_NON_PROD']]) {
                    script {
                        sh 'echo running Artifact Registry  terraform scripts'
                        if(env.BRANCH_NAME == 'main') {
                            dir("ops/ArtifactRegistry/prod") {
                                sh 'terraform --version'
                                sh 'terraform init '
                                sh 'terraform plan '
                                //sh 'terraform apply -auto-approve'
                            }
                        } else if(env.BRANCH_NAME == 'test') {
                            dir("ops/ArtifactRegistry/uat") {
                                sh 'terraform --version'
                                sh 'terraform init '
                                sh 'terraform plan '
                                //sh 'terraform apply -auto-approve'
                            }
                        } else if(env.BRANCH_NAME == 'develop') {
                            dir("ops/ArtifactRegistry/dev") {
                                sh 'terraform --version'
                                sh 'terraform init '
                                sh 'terraform plan '
                                //sh 'terraform apply -auto-approve'
                            }
                        } 
                    }
                }*/
  
