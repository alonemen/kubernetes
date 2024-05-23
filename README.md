![image](https://github.com/alonemen/kubernetes/assets/24688850/a98d09c5-d311-43ae-a520-897f0362a325)# kubernetes
Kubernetes 安装脚本

目录定义
主目录: /datadisk
ETCD目录: ./etcd
K8S目录: ./kubernetes

部署组件
数据库
etcd
Github: https://github.com/etcd-io/etcd
版本列表: https://github.com/etcd-io/etcd/blob/main/CHANGELOG
版本下载: https://github.com/etcd-io/etcd/releases
etcd官方的定义：分布式系统中最关键数据的分布式、可靠的键值存储。
etcd是一个由CoreOS团队开源的，基于Go语言实现的，用于构建高可用的分布式键值(key-value)数据库,可以用于配置共享和服务的注册和发现

特点:
  简单：基于 gRPC 定义了清晰、面向用户的 API。
  安全：支持可选的客户端 TLS 证书自动认证特性。
  快速：每个节点可支持上万QPS读写。
  可靠：基于 Raft 算法协议保证一致性。

架构介绍
![image](https://github.com/alonemen/kubernetes/assets/24688850/faded5da-cafd-4ae1-8bc2-8e45edeac9a6)

配置介绍
查找文档: https://etcd.io/docs/v3.5/op-guide/configuration/
常用配置说明

命令介绍
  基础命令
  进阶命令
  
运行目录树
bin
  etcd
  etcdctl
  etcdutl
cfg
  etcd.conf
data
  default.etcd
log
tls
  etcd_ca.pem
  etcd_ca-key.pem
  etcd_server.pem
  etcd_server-key.pem
service
  etcd.service

部署方式
  单机安装
  集群安装
    二进制
    容器化
      docker
      kubernetes

备份与恢复
监控与告警


控制平面(master)
kube-apiserver
  - kube-apiserver.conf
  - bootstrap.kubeconfig
  - token.csv
  - etcd_ca.pem
  - etcd_ca-key.pem
  - etcd_server.pem
  - etcd_server-key.pem
  - k8s_ca-key.pem
  - k8s_ca.pem
  - k8s_kube-apiserver-key.pem
  - k8s_kube-apiserver.pem

kube-controller-manager
  - kube-controller-manager.conf
  - kube-controller-manager.kubeconfig
  - k8s_kube-controller-manager-key.pem
  - k8s_kube-controller-manager.pem   
kube-scheduler
  - kube-scheduler.conf
  - kube-scheduler.kubeconfig
  - k8s_kube-scheduler-key.pem
  - k8s_kube-scheduler.pem
kubectl
  - /root/.kube/config
  - k8s_admin-key.pem
  - k8s_admin.pem 
runtime
  - docker
  - containerd

工作平面(worker)
kubelet
  - kubelet.conf
  - kubelet-config.yml
  - kubelet.kubeconfig
  - kubelet-server*.pem
  - kubelet-client*.pem
kube-proxy
  - kube-proxy.conf
  - kube-proxy-config.yml
  - kube-proxy.kubeconfig
  - k8s_kube-proxy-key.pem
  - k8s_kube-proxy.pem
runtime
  - docker
  - containerd

架构介绍

配置介绍
命令介绍
运行目录树
bin
  [kube-apiserver]
  [kube-controller-manager]
  [kube-scheduler[
  [kubectl]
  kubelet
  kube-proxy
cfg
  [kube-apiserver.conf]
  [bootstrap.kubeconfig]
  [token.csv]
  [kube-controller-manager.conf]
  [kube-controller-manager.kubeconfig]
  [kube-scheduler.conf]
  [kube-scheduler.kubeconfig]
  kubelet.conf
  kubelet-config.yml
  kubelet.kubeconfig
  kube-proxy.conf
  kube-proxy-config.yml
  kube-proxy.kubeconfig
log
tls
  [etcd_ca.pem]
  [etcd_ca-key.pem]
  [etcd_server.pem]
  [etcd_server-key.pem]
  [k8s_ca-key.pem]
  [k8s_ca.pem]
  [k8s_kube-apiserver-key.pem]
  [k8s_kube-apiserver.pem]
  [k8s_kube-controller-manager-key.pem]
  [k8s_kube-controller-manager.pem]
  [k8s_kube-scheduler-key.pem]
  [k8s_kube-scheduler.pem]
  [k8s_admin-key.pem]
  [k8s_admin.pem]
  k8s_kube-proxy-key.pem
  k8s_kube-proxy.pem
  kubelet-server*.pem
  kubelet-client*.pem
service
  [kube-apiserver.service]
  [kube-controller-manager.service]
  [kube-scheduler.service]
  kubelet.service
  kube-proxy.service

部署方式
  单机安装
  集群安装
    二进制
    容器化
      kubeadm

备份与恢复
监控与告警




集群插件
calico/flannel
coredns
nfs-provide
metric
busybox
ingress/treafik
prometheus
kuboard
velero

