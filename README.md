# manageiq-on-kubeadm
Run ManageIQ on Kubernetes

This is a rough project to run ManageIQ on generic Kubernetes

* [ManageIQ](https://github.com/ManageIQ)
* [Kubernetes](https://github.com/kubernetes/kubernetes)

Deploy a Kubernetes cluster using [kubeadm](http://kubernetes.io/docs/getting-started-guides/kubeadm/)

Select a large worker node with 8 GB or more of RAM as the manageiq docker image is resource intensive.

Once your Kubernetes cluster is up and running download the two manifest files and apply them.

`kubectl create -f dep-manage-iq.yml`
`kubectl create -f svc-manage-iq.yml`

Access to ManageIQ is via the NodePort exposure.

Use `kubectl get svc` to determine which port the ManageIQ is being exposed on.

The using the IP of the worker node and the port from `kubectl get svc` you will be able to access the ManageIQ interface.

For additional fun add the Kubernetes cluster to ManageIQ as a Container Provider.




These are first draft and need some additional work.

Wishlist 
* Health Checks
* Ingress Controller
* Persistence
