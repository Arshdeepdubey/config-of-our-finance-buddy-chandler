# config-of-our-finance-buddy-chandler
This comprise of configuration related to the finance-buddy chandler code that has been packages in a container and is ready to be shipped to cloud.

*** kubectl apply -f k8s/deployment.yaml, store your local AWS credentials inside Kubernetes secrets: ***

kubectl create secret generic aws-credentials --from-literal=aws-access-key-id=YOUR_ACCESS_KEY
kubectl create secret generic aws-secret-access-key --from-literal=aws-secret-access-key=YOUR_SECRET_KEY

*** Before executing cd.yml, ensure the Kubernetes Secret containing your AWS credentials exists in your cluster so deployment.yml can mount them: ***

kubectl create secret generic aws-credentials \
  --from-literal=AWS_ACCESS_KEY_ID=YOUR_AWS_ACCESS_KEY \
  --from-literal=AWS_SECRET_ACCESS_KEY=YOUR_AWS_SECRET_KEY \
  -n default