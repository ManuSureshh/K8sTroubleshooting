![image](https://github.com/user-attachments/assets/7c668357-6290-44fe-9c91-c924e5ba756e)

Error is because only root can perform the `kubectl`
```
sudo su
```
```
mkdir -p /home/ubuntu/.kube
cp /root/.kube/config /home/ubuntu/.kube/config
chown -R ubuntu:ubuntu /home/ubuntu/.kube
```
```
chmod 700 /home/ubuntu/.kube
chmod 600 /home/ubuntu/.kube/config
```
And verfiry
```
su - ubuntu
```
```
kubectl get nodes
```

![image](https://github.com/user-attachments/assets/e0ea257e-75ff-49ed-81ac-be3f9dc70664)
