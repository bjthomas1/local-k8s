

<!-- ABOUT THE PROJECT -->
## About The Project

This project launches a local Kubernetes cluster (one master, two workers) with Vagrant. I use it for testing Helm chart deployments locally before provisioning into a more production-like environment.

## Getting Started

To get a local copy up and running follow these simple steps.

1. Clone the repo
   ```sh
   git clone https://github.com/bthomas1/local-k8s.git
   ```

2. Bring the cluster up
   ```sh
   vagrant up
   ```

### Prerequisites

The only requirements for this cluster deployment is to have a recent version of Vagrant and VirtualBox installed. Hardware-wise, you should have around 6GB of RAM to spare, as each node is allocated 2GB. A few CPU cores is useful, too.

The cluster will make use of the 192.168.50.0/24 subnet for VirtualBox hosts and LoadBalancer IPs. Your local PC will create a local route to this subnet, which might cause issues if your existing network uses this subnet.

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/bthomas1/local-k8s.git
   ```
2. Install NPM packages
   ```sh
   vagrant up
   ```

## Usage

Vagrant will launch three VMs according to the configuration defined in ./Vagrantfile, and then provision Kubernetes using the Ansible playbooks located under ./kubernetes-setup/

The cluster itself is barebones; the only main addition being the installation of MetalLB to support the creation of Loadbalancers that would otherwise be created by a cloud platform.


## License

Distributed under the MIT License.

## Acknowledgements

* [Based on this Kubernetes.io blog](https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/)

