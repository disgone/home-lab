# NFS Persitant Volumes

Contains Helm charts for creating persitant volumes in a k8s environment using NFS as the store.

## Requirements

Nodes utilizing the NFS volumes must have NFS utilities installed in order for them to be mounted.

`sudo apt-get install nfs-common`

A NFS share must be created and exported. For example:

```
# /etc/exports
/mnt/nfs_data *(rw,sync,no_subtree_check)

## Aftering updating the exports...
systemctl restart nfs-kernel-server
sudo exportfs -rav
```

## Install

```
# helm install {RELEASE_NAME} ./path/to/chart

helm install nfs-volume ./nfs-pv
```