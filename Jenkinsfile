pipeline
{
   agent any
    stages
    {
       stage('Ashutosh VM stage')
        {
           agent
            {
                label 'ashu-vm-node-1'
            }
            steps
            {
               sh 'echo "This is my VM."'
               sh 'echo "This is for trial"'
               sh'rm -rf Multinode1'
               sh'git clone https://github.com/ashjd1/Multinode1.git'
               stash(name: 'source')
            }
        }
      stage('Shubham VM stage')
        {
            agent
            {
               label 'ashu-VM-node-2'
            }
            steps
            {
                sh 'echo "This is shubham VM"'
                unstash(name: 'source')
                sh 'chmod 777 Multinode1/script.sh'
                sh'./Multinode1/script.sh'
            }
        }
       stage('Ashu-node-1')
        {
           agent
            {
                label 'ashu-node-1'
            }
            steps
            {
               sh 'echo "This is internal node"'
            }
        }
    }
}
