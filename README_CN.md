# kubeadm-highavailiability - 基于kubeadm的kubernetes高可用集群部署，v1.11.3

![k8s logo](images/Kubernetes.png)

---

- 该指引适用于v1.11.x版本的kubernetes集群

> v1.11.x版本支持在control plane上启动TLS的etcd高可用集群。

### 目录

1. [部署架构](#部署架构)
    1. [概要部署架构](#概要部署架构)
    1. [详细部署架构](#详细部署架构)
    1. [主机节点清单](#主机节点清单)
1. [安装前准备](#安装前准备)
    1. [版本信息](#版本信息)
    1. [所需docker镜像](#所需docker镜像)
    1. [系统设置](#系统设置)
1. [kubernetes安装](#kubernetes安装)
    1. [firewalld和iptables相关端口设置](#firewalld和iptables相关端口设置)
    1. [kubernetes相关服务安装](#kubernetes相关服务安装)
    1. [master节点互信设置](#master节点互信设置)
1. [master高可用安装](#master高可用安装)
    1. [配置文件初始化](#配置文件初始化)
    1. [kubeadm初始化](#kubeadm初始化)
    1. [高可用配置](#高可用配置)
1. [master负载均衡设置](#master负载均衡设置)
    1. [keepalived安装配置](#keepalived安装配置)
    1. [nginx负载均衡配置](#nginx负载均衡配置)
    1. [kube-proxy高可用设置](#kube-proxy高可用设置)
    1. [验证高可用状态](#验证高可用状态)
    1. [基础组件安装](#基础组件安装)
1. [worker节点设置](#worker节点设置)
    1. [worker加入高可用集群](#worker加入高可用集群)
1. [集群验证](#集群验证)
    1. [验证集群高可用设置](#验证集群高可用设置)

