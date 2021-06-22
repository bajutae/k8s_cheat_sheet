# k8s_cheat_sheet

## Kubectl autocomplete
### BASH
```
source <(kubectl completion bash) # setup autocomplete in bash into the current shell, bash-completion package should be installed first.
echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.
```

### ZSH
```
source <(kubectl completion zsh)  # setup autocomplete in zsh into the current shell
echo "[[ $commands[kubectl] ]] && source <(kubectl completion zsh)" >> ~/.zshrc # add autocomplete permanently to your zsh shell
```

### Alias
```
alias k=kubectl
complete -F __start_kubectl k
```

## 자주 쓰는 명령어 
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
```

## 시간
```
kubectl get pods --sort-by=.metadata.creationTimestamp -n bff
kubectl get pods --sort-by=.status.startTime -n bff
kubectl get nodes --sort-by=.metadata.creationTimestamp 
kubectl get deploy --sort-by=.metadata.creationTimestamp 
kubectl get events --sort-by=.metadata.creationTimestamp -n bff
```

```
kubectl exec -it  -- sh
kubectl -n kube-system edit configmap coredns
k cluster-info
kubectl get events --sort-by=.metadata.creationTimestamp -n bff
kubectl get node -o custom-columns=NAME:.metadata.name,VERSION:.status.nodeInfo.kubeletVersion
kubectl get events -n <namespace>
```