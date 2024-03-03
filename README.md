# Introduction
This is the setup for Kubernetes Metrics API

# Install K8s Metrics API
Clone the repo using the below link:  
https://github.com/iam-biswas/k8s-metrics-setup.git  

Run the below command to install the K8s Metrics API  
```shell
kubectl apply -f components.yaml
```
After installing, you will be able to see the metrics-server under `kube-system` namespace.
```shell
kubectl get po -n kube-system
```
You will see the Metrics API pod will be up and running.  

Now you can run the below command to see how much Memory and CPU your node takes.
```shell
kubectl top nodes
```
Run the below command to check the utilization for a particular pod.
```shell
kubectl top po <pod_name> -n <namespace>
```

# Issues
If you see that the Metrics API Pod is not starting up and you are getting the below error, please follow this [blog] to fix it.  
`tls: failed to verify certificate: x509: cannot validate certificate for 192.168.1.131 because it doesn't contain any IP SANs" node="accserver"`  

[blog]: https://anurag.acceleratron.in/blogs/kubernetes-metrics-troubleshoot.html
