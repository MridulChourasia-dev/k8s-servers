# Kubernetes POC - Learning Guide 🚀

**A Proof of Concept for setting up a Kubernetes cluster using Vagrant and VirtualBox - Perfect for beginners!**

---

## 📚 What is Kubernetes?

Kubernetes (K8s) is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. Think of it as an intelligent system that manages where your applications run across multiple machines.

### Key Concepts:
- **Master Node**: Controls the cluster and makes decisions
- **Worker Nodes**: Run your actual applications
- **Containers**: Lightweight, portable application packages

---

## 🎯 Learning Objectives

By the end of this project, you will understand:
- ✅ How to set up a multi-node Kubernetes cluster
- ✅ The difference between Master and Worker nodes
- ✅ How to use Vagrant for infrastructure automation
- ✅ Basic Kubernetes architecture and components

---

## 📋 Prerequisites

Before you start, install these tools:

### 1. **VirtualBox** (Virtual Machine Provider)
- Download: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
- Required for creating virtual machines
- Install and restart your computer

### 2. **Vagrant** (Infrastructure Automation)
- Download: [https://www.vagrantup.com/downloads](https://www.vagrantup.com/downloads)
- Used to define and provision VMs easily
- Install and restart your computer

### 3. **Git** (Version Control)
- Download: [https://git-scm.com/downloads](https://git-scm.com/downloads)
- For cloning this repository

### Minimum System Requirements:
- **RAM**: 8 GB (4 GB minimum, but 8 GB recommended)
- **Disk Space**: 10 GB free
- **CPU**: Virtualization support enabled in BIOS

---

## 🏗️ Cluster Architecture

```
┌─────────────────────────────────────┐
│     Kubernetes Cluster              │
│  ┌──────────────┐  ┌──────────────┐ │
│  │ Master Node  │  │ Worker Node  │ │
│  │ 192.168.56.1 │  │ 192.168.56.2 │ │
│  │ 2GB | 2 CPU  │  │ 2GB | 2 CPU  │ │
│  └──────────────┘  └──────────────┘ │
└─────────────────────────────────────┘
```

---

## 🚀 Step-by-Step Setup Guide

### Step 1: Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/k8s-poc.git
cd k8s-poc
```

### Step 2: Start the Virtual Machines
```bash
vagrant up
```
This command will:
- Download the Ubuntu image (first time only)
- Create the master node VM
- Create the worker node VM
- Configure networking between them
- **⏳ This may take 5-10 minutes on first run**

### Step 3: Connect to the Master Node
```bash
vagrant ssh master
```

### Step 4: Verify the Setup
Inside the master node, check the cluster status:
```bash
# View all nodes in the cluster
kubectl get nodes

# Check system pods
kubectl get pods --all-namespaces
```

---

## ⚙️ Configuration Details

| Component | Details |
|-----------|---------|
| **Operating System** | Ubuntu Focal 20.04 LTS |
| **Master Node IP** | 192.168.56.101 |
| **Worker Node IP** | 192.168.56.102 |
| **Master Resources** | 2GB RAM, 2 CPUs |
| **Worker Resources** | 2GB RAM, 2 CPUs |
| **Network** | Private network (192.168.56.0/24) |

---

## 💡 Common Vagrant Commands (Learn These!)

| Command | Purpose |
|---------|---------|
| `vagrant up` | Start all VMs |
| `vagrant ssh master` | Login to master node |
| `vagrant ssh worker` | Login to worker node |
| `vagrant status` | Check VM status |
| `vagrant halt` | Stop all VMs (keep them) |
| `vagrant destroy` | Delete all VMs |
| `vagrant reload` | Restart all VMs |

---

## 🔧 Useful Kubernetes Commands for Learning

```bash
# View all nodes
kubectl get nodes

# Describe a specific node
kubectl describe node master

# View all pods (all namespaces)
kubectl get pods --all-namespaces

# View cluster information
kubectl cluster-info

# View system components
kubectl get deployment --all-namespaces

# Check events (useful for debugging)
kubectl get events --all-namespaces
```

---

## 🐛 Troubleshooting

### Issue: VMs won't start
- **Solution**: Enable virtualization in BIOS (Intel VT-x or AMD-V)
- Check if VirtualBox shows errors when opening the VMs

### Issue: Not enough disk space
- **Solution**: Free up at least 10 GB on your drive
- Ubuntu image is ~3 GB, plus storage for both VMs

### Issue: SSH connection fails
- **Solution**: 
  ```bash
  vagrant ssh-config
  ```
  - Check if Vagrant can find the SSH key

### Issue: Slow performance
- **Solution**: Check if other heavy applications are running
- Increase VM resources if your system allows it

---

## 📚 Learning Resources

### Official Documentation:
- [Kubernetes Official Docs](https://kubernetes.io/docs/)
- [Vagrant Documentation](https://www.vagrantup.com/docs)
- [VirtualBox Manual](https://www.virtualbox.org/wiki/Documentation)

### Recommended Learning:
1. **Understand containers first**: Learn Docker basics
2. **Master Kubernetes concepts**: Pods, Services, Deployments
3. **Practice**: Deploy sample applications to your cluster
4. **Go deeper**: Learn about StatefulSets, ConfigMaps, Secrets

---

## 🎓 Next Steps After Setup

1. ✨ Deploy your first application to the cluster
2. 🔄 Learn about Kubernetes Deployments and Replicas
3. 📡 Explore Services and networking
4. 💾 Study persistent storage options
5. 🔐 Understand authentication and RBAC (Role-Based Access Control)

---

## 📝 Project Structure

```
k8s-poc/
├── Vagrantfile          # VM configuration
├── README.md            # This file (learning guide)
├── .gitignore           # Git ignore file
└── .vagrant/            # Vagrant state (auto-generated)
```

---

## ❓ FAQ for Students

**Q: Do I need to know Docker?**
A: Basic understanding helps, but not required. This project focuses on Kubernetes.

**Q: How long will vagrant up take?**
A: 5-10 minutes on first run, 1-2 minutes on subsequent runs.

**Q: Can I modify the cluster?**
A: Yes! Edit the Vagrantfile to add more nodes, change resources, etc.

**Q: What if my computer doesn't meet requirements?**
A: Try reducing VM resources in the Vagrantfile (memory/cpus).

---

## 📄 License

MIT License - Feel free to use and modify for learning!

---

## 🤝 Contributing

Found issues or want to improve this guide? 
Submit pull requests to help other students!

---

**Happy Learning! 🎉**
