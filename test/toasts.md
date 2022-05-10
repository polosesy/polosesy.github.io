---
sort: 2
---

# CKA Certificate

# 예상 문제

<details markdown="1">
<summary> Q1 : Deploy a pod named nginx-pod using the nginx:alpine image.
</summary>

<!--summary 아래 빈칸 공백 두고 내용을 적는공간-->

```note
Answer: 
kubectl run nginx-pod --image=nginx:alpine --restart=Never
```
</details>

<details markdown="1">
<summary> Q2 : Deploy a messaging pod using the redis:alpine image with the labels set to tier=msg.
</summary>

```note
Answer: 
kubectl run messaging --generator=run-pod/v1 --restart=Never --image=redis:alpine -l tier=msg
```
</details>




<details markdown="1">
<summary> Q3 : Create a namespace named apx-x9984574
</summary>

```note
Answer: 
kubectl create ns apx-x9984574
```
</details>


<details markdown="1">
<summary> Q4 : Get the list of nodes in JSON format and store it in a file at /opt/outputs/nodes-z3444kd9.json
</summary>

```note
Answer: 
kubectl get nodes -o=jsonpath=’{.items[*].metadata.name}’ > /opt/outputs/nodes-z3444kd9.json
kubectl get nodes -o json > /opt/outputs/nodes-z3444kd9.json
```
</details>

<details markdown="1">
<summary> Q5 : Create a service messaging-service to expose the messaging application within the cluster on port 6379.
Use imperative commands
</summary>

```note
Answer: 
Create a service messaging-service to expose the messaging application within the cluster on port 6379.
```
</details>

<details markdown="1">
<summary> Q6 : Create a deployment named hr-web-app using the image kodekloud/webapp-color with 2 replicas.
</summary>

```note
Answer: 
kubectl create deploy hr-web-app –image=kodekloud/webapp-color
kubectl scale deploy hr-web-app –replicas=2
```
</details>

<details markdown="1">
<summary> Q7 : Create a static pod named static-busybox that uses the busybox image and the command sleep 1000
Use imperative commands.
</summary>

```note
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

```note
Answer: 
kubectl run –restart=Never –image=busybox static-busybox –dry-run -o yaml –command – sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
```

</details>

<details markdown="1">
<summary> Q8 : Create a POD in the finance namespace named temp-bus with the image redis:alpine.
</summary>

```note
Answer: 
kubectl run temp-bus -n finance –image=redis:alpine –restart=Never
```
</details>

<details markdown="1">
<summary> Q9 : A new application orange is deployed. There is something wrong with it. Identify and fix the issue.
</summary>

```note
Answer: 
command sleep
```
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
