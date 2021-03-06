# CloudArchitecture
This repo contains environments I setup in the cloud (aws/azure) using automation tools like  terraform and cloudformation.
The yaml files can be found in the respective folders. Some require more context like the ones below;

## Kubernetes The Not So Hard Way
I created a cloudformation template to automate the process of manually setting up a simple kubernetes cluster on 3 ubuntu vm's( one master and two worker nodes) in a custom vpc with subnet &n internet gateway. The config was done using userdata ofcourse you will need to add the worker nodes manually(still working on a possible ssm solution).


![Photo](https://github.com/goekezie/CloudArchitecture/blob/main/AWS/thenotsohardway.png)

# Steps to set up a kubernetes cluster
These are just series of commands that can be found on the [kubernetes documentation page](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)
* Letting iptable see bridged traffic
* Installing container runtime(docker)
* Configure the Docker daemon to use systemd for the management
* installing kubeadm, kubelet and kubectl
* Setting up cluster with kubeadm
* Setting up network Addon "weave"

The first 4 steps should be carried out on all nodes while the final two steps should be carried out on just the master node.
Ps I'm  still having a hard time troubleshooting some networking issues. You could also use a vagrant template to set this up on virtualbox tho you would have to run the commands manually checkout this repo [link to repo](https://github.com/goekezie/certified-kubernetes-administrator-course) 
