1.run .sh file  each node
2.After kubeadm init run in master node we got kube config file. 

mkdir -p $HOME/.kube
cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
chown $(id -u):$(id -g) $HOME/.kube/config

3.Also got the token like this
kubeadm join 34.125.55.80:6443 --token orbf61.yliqtq6wsgwsb30m \
        --discovery-token-ca-cert-hash sha256:adf1173b4db078963bed306b98d42c8b45a56ae9a9f0c3cf99343abc062560fa 

4.after join worker node
run
kubectl get ndoes  
 we get node status

5. Implemnet CNI plugin like caliclo
kubectl apply -f calico.yaml

cluster will be ready for scheduling pod/application 
