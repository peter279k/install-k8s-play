# Install K8s playbook with Ansible

# Prerequisite

- Targeted machine should be Ubuntu 18.04+.
- Ansible has been installed.
    - If not, please check this [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-18-04) to know how to install this Ansible.
- Create devops user on targeted machine (Ansible control node).
- Ensure the devops user has root permission with `sudo`.
- Ensure it can use the SSH Key to connect remote machine with devops user.

# How to create a devops user and configure current SSH key?

- Run `sudo useradd devops -s /bin/bash -m` to create the `devops` user.
- Run `ssh-keygen -t rsa -b 4096 -f /path/to/ssh_key -q -N ""` to create a SSH private/public Key.
- Run `ssh-copy-id -i /path/to/ssh_key.pub devops@$(hostname) -p port_number` to upload SSH public key to devops user.

# Usage

- Configure own `ansible.cfg` and `inventory` files.
- Run `ansible-playbook install.yml` command to install Kubernetes packages.
- Run `ansible-playbook master.yml` command to setup Kubernetes master/cluster.
- Run `ansible-playbook worker.yml` command to setup Kuberenetes workers.
    - By default, the targeted machine is local server and running single worker.

# References

- https://www.liquidweb.com/kb/how-to-install-kubernetes-using-kubeadm-on-ubuntu-18/
- https://germaniumhq.com/2019/02/14/2019-02-14-Disabling-Swap-for-Kubernetes-in-an-Ansible-Playbook/
- https://phoenixnap.com/kb/install-kubernetes-on-ubuntu
- https://stackoverflow.com/questions/53256739/which-kubernetes-version-is-supported-in-docker-version-18-09
- https://stackoverflow.com/questions/54818913/ansible-run-kubectl-apply-kube-flannel-yml-not-work
- https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-18-04
- https://stackoverflow.com/questions/62991596/1-nodes-had-taints-that-the-pod-didnt-tolerate-in-kubernetes-cluster
