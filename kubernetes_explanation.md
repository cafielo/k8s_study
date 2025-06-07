# Kubernetes Pods and Containers Explanation

The user provided a screenshot of a UI showing a list of running pods and containers within a Kubernetes cluster.

## Key Concepts Explained

### 1. Pod (파드)
- A Pod is the smallest deployable unit of computing that can be created and managed in Kubernetes.
- It represents a group of one or more containers, which share resources like storage and networking.
- In the image, items like `coredns-6d9c745b76-wgzkx` and `frontend-6685d7df8f-bhrbs` are examples of Pod names.

### 2. Container (컨테이너)
- The actual application code runs inside a container. Each pod has one or more containers.
- The `(container)` label next to a pod name indicates the application container running within that pod.
- Container images like `coredns/coredns` or `brendanjburns/journal-server` are used to create these containers.

### 3. Pod Sandbox (파드 샌드박스)
- Also known as the "pause" container. Kubernetes starts this special container for each pod first.
- Its primary role is to hold the network namespace (like the IP address) that is shared by all other containers within the pod.
- It's a foundational part of the pod's infrastructure, not a user application. The image `rancher/mirrored-pause:3.6` is an example of a sandbox image.

## Services in the Screenshot

- **coredns**: Provides DNS services within the cluster, which is a crucial part of Kubernetes networking.
- **frontend**: Likely a pod serving the user interface or a web-based part of an application.
- **local-path-provisioner**: A component that dynamically provisions Persistent Volumes using local storage on the node.

## UI Icons

The icons next to each entry typically allow for actions such as:
- **Logs Icon (folder/document):** View the logs of the container.
- **Shell Icon (terminal/prompt):** Open a shell into the container for debugging.
- **Delete Icon (trash can):** Delete the resource.

## Summary

The image provides a dashboard view of the current state of key services (DNS, frontend, storage) running in a Kubernetes cluster, showing the structure of pods and their constituent containers. 