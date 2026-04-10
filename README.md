# Kubernetes POC

A Proof of Concept for Kubernetes cluster setup using Vagrant and VirtualBox.

## Overview

This project sets up a basic Kubernetes cluster with:
- **1 Master Node** (192.168.56.101)
- **1 Worker Node** (192.168.56.102)

## Prerequisites

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Setup

1. Clone this repository
2. Navigate to the project directory
3. Run the following command to start the VMs:
   ```bash
   vagrant up
   ```

4. SSH into the master node:
   ```bash
   vagrant ssh master
   ```

## Configuration

- **OS**: Ubuntu Focal 20.04 LTS
- **Master Resources**: 2GB RAM, 2 CPUs
- **Worker Resources**: 2GB RAM, 2 CPUs
- **Private Network**: 192.168.56.0/24

## License

MIT
