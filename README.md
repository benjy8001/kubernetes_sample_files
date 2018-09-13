Sample files in order to get autoscallable nginx app.
========

How to use
-----

For testing, you need to install minikube.

# Enable some addons

	$ minikube addons enable ingress
	$ minikube addons enable heapster
	$ minikube addons enable metrics-server
	$ minikube addons enable dashboard

# Apply yaml files

	$ kubectl apply -f nginx.yaml
	$ kubectl apply -f nginx-svc.yaml
	$ kubectl apply -f nginx-ingress.yaml
	$ kubectl apply -f nginx-hpa.yaml

# Show conf

	$ kubectl get deployements
	$ kubectl get pods
	$ kubectl get services
	$ kubectl get ingress
	$ kubectl get hpa

# Get measures of a pod

	$ kubectl top pod nginx-[...]

	$ kubectl describe nodes/minikube

# Bench and test HPA

	$ ab.exe -n 1000000 -c 1000 http://192.168.99.100.nip.io/
	$ kubectl get hpa -w
