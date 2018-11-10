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
apt-get update && apt-get install openssh-client -y
kubectl cp ~/.ssh/id_rsa aks-ssh-554b746bcf-kbwvf:/id_rsa
chmod 0600 id_rsa
ssh -i id_rsa azureuser@10.240.0.4
```


