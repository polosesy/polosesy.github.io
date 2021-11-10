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
  
Cloud Native Application = Saas (sofrware as a service)
 핵심은 서비스 
 어플리케이션을 여러개의 서로 독립적인 서비스로 구분


기존 어플리케이션 아키텍쳐
Scale UP(스펙을 업)
Monolithic (하나의 어플리케이션에 통으로)
Stateful 
Tightly coupled(전체가 묶여있어 하나가 변경되면 관련된 모든것이 바뀌어야한다,의존성)

마이크로서비스 아키텍쳐
Scale out(성능 향상이 아닌 수평적 확장)

MSA 서비스 장점.
하나의 리전이 아닌 각각 다른 리전에 서비스를 베포하여 서비스의 중단 없이 서비스가 가능

Microservices 
12-Factors
Multi-tenancy
PaaS
Container


Auto 스케일링,과 replecation 은 연관 되어있다.

에플리케이션을 서비스로 분리
서비스 
사용자 관리(인터페이스- REST,Thnift,Protocol buffer,AMQP)
사용자 데이터
업무상의 기능 또는 역할을 하나의 기능 무음으로 개발된 컴포넌트 > 한가지의 역할만 수행
REST API들을 통해 서비스들의 기능을 제공하고 사용
데이터를 공유하지 않고 서비스별로 독립적으로 저장.

임베디드 데이터베이스를 사용할때 클러스터링 되어있지 않다면 데이터 저장 영역은 공유하도록 한다.

모놀리틱한 서비스를 > 마이크로 서비스로 변경할때 (쿼리가 중요) 
기존 프로젝트를 바꾸는건 힘들다.
	어플리케이션 영향도 분석 툴

Microservices 모델링 (방법론적)
  Domain Driven Design
  Bounded Context
  Contract-First(API-First) Design (API를 세분화,  ex)기업의 조직의 세분화 처럼,)
  Decomposed database
  Event-Driven Archiecture (상호간의 커뮤니케이션을 위한 이벤트들을 어떻게 처리할 것 인가)

마이크로서비스를 이해하기 위해
도메인에 대한 이해
애플리케이션의 바운더리 이해
API

유저시나리오 대로 구현 ( TDD 방식 개발)
로드러너(부하테스트)
Jmeter(부하테스트)

마이크로서비스를 어떻게 구성하고 배치할 것 인가 (설계)

Redis의 용도 
세션 클러스터링
데이터베이스를 캐싱해준다.
불필요한 패치 동작을 줄여 (DB의 부담을 줄여준다)

Aggregator - 하나를 받아서 분기를 해준다.
proxy - 데이터 캐싱 역할도 해준다. 들어온 곳을 하나로 만들어주고 일반적으로 보안적으로도 사용, 내부를 바로 접근할 수 없도록 프록시를 거쳐 서비스에 접근하도록 한다.

서비스 체이닝,서비스의 흐름이 보여야한다.
업무 프로세스가 거쳐가는 단계가 보여야한다.
Istio,ArogoCD등(service mesh)을 사용하는 이유는 서비스의 흐름을 파악하기위해, 가시성을 갖기위해,

데이터 베이스를 구성하는 방법
Isolated
Semi-Shared (MSA에서 많이 사용)
Shared

Poster SQL 사용하는 이유(SaaS형 애플리케이션의 적합)
네임스페이스 별로 다른 네임스페이스를 정의하고 다른 별도의 스페이스를 사용할 수 있다.
멀티 테넌트형 

다른 DB는 테넌트 ID를 table에 지정하여 사용



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
