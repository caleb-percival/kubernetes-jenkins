pipeline{

    agent any

        stages{

            stage("k8s"){

                steps{

                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'kubernetes_secret', namespace: 'default', serverUrl: 'https://B850EFC5866A758AAEB8B86F6836910F.yl4.eu-west-2.eks.amazonaws.com']])

                    {

                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'

                    sh 'chmod u+x ./kubectl'

                    sh './kubectl get nodes'

                    sh './kubectl create -f pod.yaml'

                    sh './kubectl get pods'

                    }

                }    

        }

    }
}