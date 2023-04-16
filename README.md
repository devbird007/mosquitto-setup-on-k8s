# mosquitto-project

This demonstrates how to persist the `configmap` and `secret` components
as volumes in kubernetes.

This is useful for attaching secret files and config files to applications
like **mosquitto** that will need them.

The `configmap` and `secret` components have to be created before the pod
to avoid errors.

In the deployment file, you can observe that the volumes are attached to
the pod, then mounted onto the containers that will need them, in this case
there is only one container.

You can confirm the success of this configuration by checking the needed 
directories in the container. You enter into the container with the
following command:  

`kubectl exec -it <<pod name>> -- /bin/sh` 
