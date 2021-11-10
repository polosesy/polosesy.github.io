---
sort: 1
---

# 11월 10일 MSA강의 
비인증 open API의 예 ex) 파파고
임베디드 H2DB

Microservice 개발 (TDD기반)

 - Spring Boot 2.x
 - Reds Session
 - Embedded H2 Database. ORM(Object releation... )
 - Embedded Tomcat (JNDI Data source)
 - Hibermate 
 - Rest API
   - RestController.
   - MVC(Model(DB,DTO(data trance object),VO(view object - json,xml,jsp..)) view control)

MSA 개발 > 빌드/패키징/테스트 > 이미지 제작 > 테스트 (Docker, k8s) > Docker Regi에 push(등록) > Helm Chart 제작 
개발 Python(Flask)

Azure 구독신청
 사용할 자원 (후에 Terraform 자동생성)
 1. vNET
 2. VM(BootStrap(Jenkins,Nexus,Gitlab,EFK,SonaCube),Master1~2,Worker1~3,) > AKS(Kubernetes > KubeSpray로 구성)
    Local VM Ubuntu Terraform 구성 > Azure 
 4. ACR (azure container registry)
 5. Monitering(Grafana, Prometeus,wevescope,instana,APM)

Service Mesh (운영용으로 사용할만큼 좋은가?, 비용/자원효율성? 부분에 대해서 아직 도전을 받는다)
  Istio + envoy + Kiali
  MSA APP > Deploy
  ArogoCD + GitOps 
  개념,개용 활용 > Spring Cloud
  
 MSA 1세대 : Spring Clud/boot (VM or Container) | 운영 서비스 중점.
 MSA 1.5세대 : Spring Cloud/ + GitOps + K8s(Helm,ArogoCD,FlexCD) | 운영화.
 MSA 2세대 : Spring Clud/boot + Vert.X,AKKA(클러스터 기반 고성능 분산,서비스를 해주는것) + K8s | 시범,테스트,개발. (운영은 힘들다)
 MSA 3세대 : SideCar ~ Istio + Envoy(proxy) + K8s | 시범,테스트,개발.
 MSA 4세대 : SideCar ~ Istio + Envoy(proxy) + K8s + serverless(클라우드제공) | 시범,테스트,개발. 
 
 OCP(Service Mesh)도 현재는 시범적
  



# Header 1



## Header 2


### Header 3



#### Header 4

- This is an unordered list following a header.
- This is an unordered list following a header.
- This is an unordered list following a header.

##### Header 5

1. This is an ordered list following a header.
2. This is an ordered list following a header.
3. This is an ordered list following a header.

###### Header 6

| What    | Follows  |
| ------- | -------- |
| A table | A header |
| A table | A header |
| A table | A header |

---

There's a horizontal rule above and below this.

---

Here is an unordered list:

- Salt-n-Pepa
- Bel Biv DeVoe
- Kid 'N Play

And an ordered list:

1. Michael Jackson
2. Michael Bolton
3. Michael Bublé

And an unordered task list:

- [x] Create a sample markdown document
- [x] Add task lists to it
- [ ] Take a vacation

And a "mixed" task list:

- [ ] Steal underpants
- ?
- [ ] Profit!

And a nested list:

- Jackson 5
  - Michael
  - Tito
  - Jackie
  - Marlon
  - Jermaine
- TMNT
  - Leonardo
  - Michelangelo
  - Donatello
  - Raphael

Definition lists can be used with HTML syntax. Definition terms are bold and italic.

<dl>
    <dt>Name</dt>
    <dd>Godzilla</dd>
    <dt>Born</dt>
    <dd>1952</dd>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
    <dt>Color</dt>
    <dd>Green</dd>
</dl>

---

Tables should have bold headings and alternating shaded rows.

| Artist          | Album          | Year |
| --------------- | -------------- | ---- |
| Michael Jackson | Thriller       | 1982 |
| Prince          | Purple Rain    | 1984 |
| Beastie Boys    | License to Ill | 1986 |

If a table is too wide, it should condense down and/or scroll horizontally.

<!-- prettier-ignore-start -->

| Artist            | Album           | Year | Label       | Awards   | Songs     |
|-------------------|-----------------|------|-------------|----------|-----------|
| Michael Jackson   | Thriller        | 1982 | Epic Records | Grammy Award for Album of the Year, American Music Award for Favorite Pop/Rock Album, American Music Award for Favorite Soul/R&B Album, Brit Award for Best Selling Album, Grammy Award for Best Engineered Album, Non-Classical | Wanna Be Startin' Somethin', Baby Be Mine, The Girl Is Mine, Thriller, Beat It, Billie Jean, Human Nature, P.Y.T. (Pretty Young Thing), The Lady in My Life |
| Prince            | Purple Rain     | 1984 | Warner Brothers Records | Grammy Award for Best Score Soundtrack for Visual Media, American Music Award for Favorite Pop/Rock Album, American Music Award for Favorite Soul/R&B Album, Brit Award for Best Soundtrack/Cast Recording, Grammy Award for Best Rock Performance by a Duo or Group with Vocal | Let's Go Crazy, Take Me With U, The Beautiful Ones, Computer Blue, Darling Nikki, When Doves Cry, I Would Die 4 U, Baby I'm a Star, Purple Rain |
| Beastie Boys      | License to Ill  | 1986 | Mercury Records | noawardsbutthistablecelliswide | Rhymin & Stealin, The New Style, She's Crafty, Posse in Effect, Slow Ride, Girls, (You Gotta) Fight for Your Right, No Sleep Till Brooklyn, Paul Revere, Hold It Now, Hit It, Brass Monkey, Slow and Low, Time to Get Ill |

<!-- prettier-ignore-end -->

---

Code snippets like `var foo = "bar";` can be shown inline.

Also, `this should vertically align` ~~`with this`~~ ~~and this~~.

Code can also be shown in a block element.

```
var foo = "bar";
```

Code can also use syntax highlighting.

```javascript
var foo = "bar";
```

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```javascript
var foo =
  "The same thing is true for code with syntax highlighting. A single line of code should horizontally scroll if it is really long.";
```

Inline code inside table cells should still be distinguishable.

| Language   | Code               |
| ---------- | ------------------ |
| Javascript | `var foo = "bar";` |
| Ruby       | `foo = "bar"`      |

---

Small images should be shown at their actual size.

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

Large images should always scale down and fit in the content container.

![Branching](https://guides.github.com/activities/hello-world/branching.png)

```
This is the final element on the page and there should be no margin below this.
```
