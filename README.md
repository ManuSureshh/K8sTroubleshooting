# K8sTroubleshooting

![image](https://github.com/user-attachments/assets/1f31efe6-9c56-4949-86d9-1b649f4bad59)
- The error you're seeing indicates that kubectl is unable to connect to the Kubernetes API server, which usually runs on port 6443 (not 8080, which is the default for local testing).
- The error messages suggest that kubectl is attempting to connect to localhost:8080, which is not the correct API server endpoint for a Kubernetes cluster.


- Check the status of Kubernetes API Server.
  ```
  sudo systemctl status kube-apiserver
  ```
  
- If not running, try to restart it.
  ```
  sudo systemctl restart kube-apiserver
  ```

![image](https://github.com/user-attachments/assets/7d21d623-a512-47e1-b378-7979ead2a670)

The above error shows, the api-server is not running as a standalone systemd on your local machine.
- Check the Status of the Static Pods:
  ```
  sudo crictl ps -a | grep kube-apiserver
  ```
