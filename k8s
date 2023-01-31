## K8S componets
- node: maintaining running pods and providing k8s runtime environment
	- kubelet: make sure that containers are running in a pod, ensure the containers are running and healthy
	- kube-proxy: network rules allow network communications to pods
	- container runtime: containers, CRI-O
- pod: 托管在pod，pod是应用负载的组件
- control plane：资源管理调度，组件通常单独装在一台机器，不会运行用户容器
	- kube-apiserver: expose k8s API, front end for control plane，可以横向扩展，run several instances and balance traffic between those instances
	- etcd: consistent end and high-available key value store. Store k8s cluster data
	- kube-scheduler: watches for newly created Pods with no assigned node and selects a node for them to run on
	- kube-controller-manager
		- Node controller: noticing and responding when nodes go down
		- Job controller: create pods to run one-off tasks
		- EndpointSlice controller: populate endpointSlice(provide a link between Services and Pods)
		- ServiceAccount controller: create default Service Accounts for new namespaces
	- cloud controller manager: link cluster into your cloud provider's API
- Addons: k8s resources(DaemonSet, Deployment, etc) to implements cluster features
	- DNS: DNS server
	- Web UI(Dashboard)
	- Container Resource Monitoring: time-series metrics in DB and provide UI for browsing
	- Cluster-level logging



## k8s objects
persistent entities, define with yaml, represent state of your cluster
- what containerized apps are running(and on which nodes)
- the resources available to those applications
- the policies around how those applications behave(restart, upgrade, and fault-tolerance)



Object spec and status:
- spec: desired state
- status: current state

The control plane continually and actively manages every object's actual state to match the desired state you supplied

Provide the information to kubectl in a .yams file, kubectl converts the information to Jason when making API request

`kubectl apply -f xxx.yaml`

Required fields
