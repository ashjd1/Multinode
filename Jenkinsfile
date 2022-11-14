pipeline

{

    agent any

    stages

    {

        stage('stage 1')

        {

           agent

            {

                label 'myvm'

            }

            steps

            {

                sh'git init'

                sh'rm -rf first'

                sh'git clone https://github.com/ashjd1/Multinode1.git'

                sh 'echo "multi-node-demo-1"'

                stash(name: 'source')

            }

        }

        stage('stage 2')

        {

            agent

            {

                label 'withother'

            }

            steps

            {

                sh 'echo "multi-node-demo-2"'

                unstash(name: 'source')

                sh'pwd'

                sh'cd first/'

                sh'pwd'

                sh 'chmod 777 first/script.sh'

                sh'pwd'

                sh'./first/script.sh'

            }

        }

    }

}
