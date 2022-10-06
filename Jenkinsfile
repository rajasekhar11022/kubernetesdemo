pipeline{

    agent any

    stages{

        stage ('Create Namespace') {
            steps {
			    sh "kubectl create namespace dev"
            }
        }
		stage ('Kubectl Apply Dry Run') {
            steps {
			    sh "kubens dev"
				sh "kubectl apply -n dev -f nginx-ingress.yml -o yaml --dry-run"
            }
        }
		stage ('Kubectl Apply') {
            steps {
			    sh "kubectl apply -n dev -f nginx-ingress.yml"
            }
        }
	}
}	