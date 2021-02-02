# Install K8s playbook with Ansible

# Prerequisite

- Targeted machine should be Ubuntu 18.04+.
- Ansible has been installed
- Create devops user on targeted machine (Ansible control node)
- Ensure the devops user has root permission with `sudo`
- Ensure it can use the SSH Key to connect remote machine with devops user

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
