pipeline

{

    agent any

    stages

    {

        stage('My VM')

        {

           agent

            {

                label 'ashu-vm-node-1'

            }

            steps

            {

                sh'git init'

                sh'rm -rf Multinode1'

                sh'git clone https://github.com/ashjd1/Multinode1.git'

                sh 'echo "multi-node-demo-1"'

                stash(name: 'source')
            }
        }
      stage('shubham VM')
        {
            agent
            {
               label 'ashu-VM-node-2'
            }
            steps
            {
              sh 'echo "multi-node-demo-2"'
                unstash(name: 'source')
                sh'#cd first/'
                sh'pwd'
                sh 'chmod 777 Multinode1/script.sh'
                sh'pwd'
                sh'./Multinode1/script.sh'

            }

        }

    }

}
