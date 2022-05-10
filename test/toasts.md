---
sort: 2
---

# CKA Certificate

# 예상 문제

<!-- 양식 

<details markdown="1">
<summary> Q.1 : 
</summary>

```
Answer: 

```
</details>

-->


<details markdown="1">
<summary> Q.1 : Deploy a pod named nginx-pod using the nginx:alpine image.
</summary>

<!--summary 아래 빈칸 공백 두고 내용을 적는공간-->

```
Answer: 
kubectl run nginx-pod --image=nginx:alpine --restart=Never
```
</details>

<details markdown="1">
<summary> Q.2 : Deploy a messaging pod using the redis:alpine image with the labels set to tier=msg.
</summary>

```
Answer: 
kubectl run messaging --generator=run-pod/v1 --restart=Never --image=redis:alpine -l tier=msg
```
# ttps://github.com/kubernetes/kubernetes/pull/68132 더이상 --generator 기능은 지원하지 않음.
</details>




<details markdown="1">
<summary> Q.3 : Create a namespace named apx-x9984574
</summary>

```
Answer: 
kubectl create ns apx-x9984574
```
</details>


<details markdown="1">
<summary> Q.4 : Get the list of nodes in JSON format and store it in a file at /opt/outputs/nodes-z3444kd9.json
</summary>

```
Answer: 
kubectl get nodes -o=jsonpath=’{.items[*].metadata.name}’ > /opt/outputs/nodes-z3444kd9.json
kubectl get nodes -o json > /opt/outputs/nodes-z3444kd9.json
```
</details>

<details markdown="1">
<summary> Q.5 : Create a service messaging-service to expose the messaging application within the cluster on port 6379.
Use imperative commands
</summary>

```
Answer: 
Create a service messaging-service to expose the messaging application within the cluster on port 6379.
```
</details>

<details markdown="1">
<summary> Q.6 : Create a deployment named hr-web-app using the image kodekloud/webapp-color with 2 replicas.
</summary>

```
Answer: 
kubectl create deploy hr-web-app --image=kodekloud/webapp-color
kubectl scale deploy hr-web-app --replicas=2
```
</details>

<details markdown="1">
<summary> Q.7 : Create a static pod named static-busybox that uses the busybox image and the command sleep 1000
Use imperative commands.
</summary>

```
apiVersion: v1

kind: Pod

metadata:

  name: static-busybox

spec:

  containers:

   - name: static-busybox

​     image: busybox

​     command: ["sleep"]

​     args: ["1000"]

```
#참조
https://kubernetes.io/docs/tasks/configure-pod-container/static-pod/#static-pod-creation
https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/

```
Answer: 
# command 수정 필요
kubectl run -–restart=Never -–image=busybox static-busybox -–dry-run -o yaml -–command –sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
```

</details>

<details markdown="1">
<summary> Q.8 : Create a POD in the finance namespace named temp-bus with the image redis:alpine.
</summary>

```
Answer: 
kubectl run temp-bus -n finance –image=redis:alpine –restart=Never
```
</details>

<details markdown="1">
<summary> Q.9 : A new application orange is deployed. There is something wrong with it. Identify and fix the issue.
</summary>

```
Answer: 
command sleep
```
</details>



<details markdown="1">
<summary> Q.10 : Expose the hr-web-app as service hr-web-app-service application on port 30082 on the nodes on the cluster
The web application listens on port 8080.
</summary>

```
Answer: 
kubectl expose deploy hr-web-app –name=hr-web-app-service –port=33082
kubectl expose deployment hr-web-app --type=NodePort --port=8080 --name=hr-web-app-service --dry-run -o yaml > hr-web-app-service.yaml
```
</details>


<details markdown="1">
<summary> Q.11 : Create a Persistent Volume with the given specification.
</summary>

```
Answer: 
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-analytics
spec:  
  capacity:    
  storage: 100Mi  
  accessModes:    
​    - ReadWriteMany  
  hostPath:    # directory location on host    
  path: /pv/data-analytics
```
#참조 
https://kubernetes.io/docs/concepts/storage/persistent-volumes/#types-of-persistent-volumes
https://kubernetes.io/docs/concepts/storage/volumes/
</details>

<!-- 주석 처리 

THIS IS TOO LONG, NEED UPDATE! HERE IS SOME IDEAS:

- https://primer.style/css/components/box
- https://primer.style/css/components/toasts



Markdown is supported, Text can be **bold**, _italic_, or ~~strikethrough~~. [Links](https://github.com) should be blue with no underlines

`inline code`

[`inline code inside link`](./)
```

```note
This is note2
```

```note
This is note3
```

```tip
It’s bigger than a bread box.
```

```tip
It’s tip 2
```

```warning
Strong prose may provoke extreme mental exertion. Reader discretion is strongly advised.
```

```danger
Mad scientist at work!
```
-->
