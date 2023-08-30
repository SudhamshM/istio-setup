# Istio setup in local Kubernetes cluster
Basic istio setup for local Kubernetes cluster

- Walkthrough of Tech With Nana's YouTube video [here!](https://www.youtube.com/watch?v=voAyroDb6xk)

1. Download istio and setup [from this guide.](https://istio.io/latest/docs/setup/getting-started/#download)
   - Add to path and test with command `istioctl`
2. Install istio into the cluster and verify
   - Check `istio-system` namespace is created with `kubectl get namespaces`
   - Check istio pods are present in that namespace `kubectl get po -n istio-system`
3. Deploy a simple microservices app
   - Use a sample from Google [found here.](https://github.com/GoogleCloudPlatform/microservices-demo/blob/main/release/kubernetes-manifests.yaml)
   - Run `kubectl apply -f kubernetes-manifest.yaml` to deploy the app
   - Verify pods, services, replica set and other objects are created