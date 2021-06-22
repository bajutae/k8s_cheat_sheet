# k8s_cheat_sheet

```
kubectl describe configmap -n kube-system aws-auth
kubectl delete pods <podname> --grace-period=0 
k label node spotinst.io/node-lifecycle
journalctl -xfu kubelet
k describe pod/bff-common-prd-tag-20201013-160000-5-7b9ccd66f5-kp4mc -n bff
kubectl get events -n <namespace명>
k get events 
k exec -it bff-common-prd-tag-20201013-160000-3-866b5bddcf-5scvk -n bff -- sh
kubectl describe pod <pod명> -n <namespace명>
kubectl logs pod <pod 명>

## time 
kubectl get pods --sort-by=.metadata.creationTimestamp -n bff
kubectl get pods --sort-by=.status.startTime -n bff
kubectl get nodes --sort-by=.metadata.creationTimestamp 
kubectl get deploy --sort-by=.metadata.creationTimestamp 
kubectl get events --sort-by=.metadata.creationTimestamp -n bff


kubectl exec -it  -- sh
kubectl -n kube-system edit configmap coredns
k cluster-info
kubectl get events --sort-by=.metadata.creationTimestamp -n bff
kubectl get node -o custom-columns=NAME:.metadata.name,VERSION:.status.nodeInfo.kubeletVersion
kubectl get events -n <namespace>
```