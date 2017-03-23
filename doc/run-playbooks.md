# Run the playbooks to install OpenStack

## Standalone

1. 进入/etc/ansible/roles/ansible-role-openstack/inventory/dev-single目录

2. 安装部署ceph
      
    ansible-playbook -i dev-openstack.ini ../../playbooks/setup-ceph.yml

3. 单机模式部署OpenStack
  
    ansible-playbook -i dev-openstack.ini ../../playbooks/setup-single-controller.yml
