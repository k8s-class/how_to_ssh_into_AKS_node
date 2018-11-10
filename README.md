# How to ssh into AKS node for troubleshooting


```
kubectl get nodes -o wide
kubectl drain aks-default-24143415-2 --grace-period 600 --ignore-daemonsets
kubectl get nodes -o wide
az aks show --resource-group EpicK8s --name Epick8s --query nodeResourceGroup -o tsv
az vm user update   --resource-group MC_Epick8s_Epick8s_centralus   --name aks-default-24143415-2   --username azureuser   --ssh-key-value ~/.ssh/id_rsa.pub
az vm list-ip-addresses --resource-group MC_Epick8s_Epick8s_centralus -o table
kubectl run -it --rm aks-ssh --image=debian
az vm user update   --resource-group MC_Epick8s_Epick8s_centralus   --name aks-default-24143415-2   --username azureuser   --ssh-key-value ~/.ssh/id_rsa
kubectl run -it --rm aks-ssh --image=debian
```


