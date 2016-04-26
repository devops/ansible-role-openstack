# Ansible Role: openstack

Installs and configures openstack on CentOS/RedHat.

## 部署要求

`前提条件： 一定要自己定制ceph以及centos的安装源，用默认的CentOS以及Ceph的官方源无法完成安装，有依赖冲突.`

`硬件要求： 3台Controller 2台Compute 3台Ceph(mon+osd)`

`目前只支持HA模式的部署必须三个节点`

##  使用说明
`文档相对简单，细节请看代码`

安装需要的的roles

    ansible-galaxy install -r requirements.yml -p roles

建立inventory目录，并创建环境相关的文件(可参考inventory/dev中的内容进行修改)

部署Ceph(可选)

    ansible-playbook -i dev-openstack.ini -u root -c paramiko dev-ceph.yml

部署OpenStack Controller节点

    ansible-playbook -i dev-openstack.ini -u root -c paramiko dev-openstack-controller-ha.yml

部署OpenStack Compute节点

    ansible-playbook -i dev-openstack.ini -u root -c paramiko dev-openstack-compute.yml

## 问题说明

- 如果任务失败，必须将系统重装或是清理干净后重新执行部署任务

## License

MIT / BSD

## Author Information

Z.
