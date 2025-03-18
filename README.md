# Kubernetes 101

In this repository. I will talk about my knowledge and my perspective of this tool.

As we know Kubernetes has a hierarchical approach which is layered for better control and communication mechanism. To learn this layered approach, we can start from the small component of the Kubernetes which is `pods`. 

### What is Pod?

Pod is the smallest component of the kubernetes which runs container/s. Since we cleared that out, "How this pods actually managed?" you may ask. To manage all of this pods, kubernetes uses a node called the `Worker Node` which controls the pods inside it. Since there could be more than 1 `Worker Node` in our system, we have to control this nodes with `Master Node`. It's not rocket science, guys, let's not start building spaceships just yet!

### We Know About Nodes, What Is Cluster?

The cluster is at the top of the hierarchy in our Kubernetes system. Everything is organized under the `Cluster`, including the Master Node and Worker Nodes. Therefore, the cluster is a crucial part of our system.

