# NFS Persistent Volumes

Contains Helm charts for creating persistent volumes in a Kubernetes environment using NFS as the storage backend.

## Requirements

Nodes utilizing the NFS volumes must have NFS utilities installed in order for them to be mounted.

`sudo apt-get install nfs-common`

A NFS share must be created and exported. For example:

```
# /etc/exports
/mnt/nfs_data *(rw,sync,no_subtree_check)

## After updating the exports...
systemctl restart nfs-kernel-server
sudo exportfs -rav
```

## Install

```
# helm install {RELEASE_NAME} ./path/to/chart

helm install nfs-volume ./nfs-pv
```
