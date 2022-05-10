---
sort: 2
---

# CKA Certificate


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

<!--summary 아래 빈칸 공백 두고 내용을 적는공간-->

```note
Answer: 
kubectl run messaging --generator=run-pod/v1 --restart=Never --image=redis:alpine -l tier=msg
```
</details>




주석 처리 : \\<!-- & -->
주석은\\<!--와 -->로 감싸주어서 <!-- 주석처리 -->와 같이 처리한다.

<!--

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
