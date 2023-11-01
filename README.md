### pv & pvc asses mode 

In Kubernetes, the "access mode" of a Persistent Volume (PV) or Persistent Volume Claim (PVC) specifies how the volume can be accessed by pods running in your cluster. There are three commonly used access modes:

### ReadWriteOnce (RWO):

This mode allows the volume to be mounted as read-write by a single node (pod) at a time. It's often used for storage that can only be attached to one pod and is suitable for use cases where data needs to be modified by a single pod.

### ReadOnlyMany (ROX):

This mode allows the volume to be mounted as read-only by multiple nodes (pods) simultaneously. It's typically used when you want multiple pods to access the data in read-only mode, but not modify it. For example, you might use this for shared configuration files or static assets.

### ReadWriteMany (RWX):

This mode allows the volume to be mounted as read-write by multiple nodes (pods) simultaneously. It's used for shared storage where multiple pods need both read and write access to the data. NFS (Network File System) and other network-based storage solutions often support this access mode.


## persistentVolumeReclaimPolicy

### Retain:

When the PVC is deleted or released, the PV and the associated storage resources are not automatically deleted. The storage remains intact, and it is the administrator's responsibility to manually reclaim and delete the resources.

### Delete:

When the PVC is deleted or released, the PV and the associated storage resources are automatically deleted. This option is suitable for scenarios where the storage should be released and the resources reclaimed automatically.

### Recycle (Deprecated):

This policy is deprecated and not recommended for use. It used to be a way to perform basic cleanup of the storage, but it has been deprecated in favor of more advanced solutions like dynamic provisioning and storage classes.

