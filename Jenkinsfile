pipeline{
    agent{
        label 'ANSIBLE'
    }
    stages{
        stage ('SCM'){
            step{
                branch 'master'
                git 'https://github.com/rvkrthk/jenkins-tomcat-pipeline.git'
            }
        }
        stages ('ANSIBLE'){
            steps{
                sh 'ansible -i inventory -m ping all'
                sh 'ansible-playbook -i inventory gameoflifedeploy.yaml'
            }
        }

    }
}