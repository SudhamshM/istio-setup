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
4. Configure namespace and label to allow proxy injection by istio
   - Run `kubectl label ns default istio-injection=enabled`
   - Delete current manifest application and re-run the apply command
   - Verify 2 containers are there for each pod (extra container is for envoy proxy)
5. Install addons and monitoring tools
   - Get them from istio [here.](https://istio.io/latest/docs/ops/integrations/)
   - Test with Kiali dashboard locally
* Make sure the `app: <NAME>` label exists in the manifest to visualize in Kiali