pipeline{
    agent{
        label 'ANSIBLE'
    }
    stages{
        stage ('SCM'){
            steps{
                branch 'master'
                git 'https://github.com/rvkrthk/jenkins-tomcat-pipeline.git'
            }
        }
        stage ('ANSIBLE'){
            steps{
                sh 'ansible -i inventory -m ping all'
                sh 'ansible-playbook -i inventory gameoflifedeploy.yaml'
            }
        }

    }
}