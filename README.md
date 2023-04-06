# 코인거래소 ABCbit 3Tier Architecture 구축
(🥇First prize) Semi team Project - based on AWS
└ 고가용성 및 부하분산을 위한 3Tier(WEB, WAS, DB) Architecture 구축 프로젝트

# 목차
[1. 개요](#개요)

[2. 메인 구축 과정](#메인-구축-과정)

<br/>

## 개요
#### - AWS의 서비스를 바탕으로 스프링 오픈 소스를 활용한, 3Tier Architecture구축 프로젝트
#### - 또한, 보안 및 웹 페이지의 안정성을 위해 세션 클러스터링과 Crontab을 활용한 로그 관리, CDN(Content Delivery Network)을 구현

<br/>

### 구축 인원 및 기간
<b> - 기간 : 2022-08-29 ~ 2022-09-16 (총 3주) </b> <br/>
<b> - 인원 : 5명 (인프라 구축 5명) </b>

<br/>

### 구축환경
```
1. Notion, Slack, Google Tools(Sheets, Slides, Meet, Chat)를 활용한 협업
2. AWS의 서비스를 기반으로 하여 터미널 프로그램(MobaXterm, Putty, Xshell)을 통해 서버 접속, Spring프로젝트 운영 관리
```
![image](https://user-images.githubusercontent.com/84059211/212465172-da9c20cc-e6ef-4f57-aff9-c002b8db74fa.png)

<br/>

### 🙌 담당 역할 🙌
#### 1. 확장성이 존재하는 was서버의 세션 불일치 극복을 위해 Amazon Elasticache를 사용해서 스켈레톤 Spring boot 프로젝트의 소스코드를 수정하여 Session Cluster 구성
#### 2. 팀에서 정한 로그 관리 기준을 바탕으로 S3 백업을 위한 crontab 구성 및 shell 스크립트 작성
#### 3. AWS 인프라 리소스 생성 및 관리


<br/>

### 시장 분석
```
1. 많은 금융 기업들이 온프레미스 환경에서 클라우드 환경으로 옮김
2. ABCbit 또한, 아래와 같은 이유로 클라우드 환경을 선택
```
![image](https://user-images.githubusercontent.com/84059211/212464910-5fef4c1d-de15-4eb6-9bd9-7d36374e12c0.png)

<br/>

### 고객 요구사항 및 대응 방안
```
보안 강화, 지속적인 모니터링, CDN서비스를 이용한 대량의 트래픽 처리, 자동 로그 관리 등의 요구사항을 바탕으로 프로젝트 진행 
```
![image](https://user-images.githubusercontent.com/84059211/212464883-c92f3f0c-bd87-4922-8d7e-f7a8b5a00e92.png)
![image](https://user-images.githubusercontent.com/84059211/212464891-24f99dfe-45d7-4871-8445-09e41cc27152.png)

<br/><br/>

## 메인 구축 과정
### Solution Architecture
![image](https://user-images.githubusercontent.com/84059211/212464998-2c844cef-1be6-455d-837b-d77c7e6cd237.png)

<br/>

### ABCbit Service
```
[참고] https://github.com/spring-projects/spring-petclinic
스프링 예제 펫클리닉을 활용한 웹서비스 구축
```
![image](https://user-images.githubusercontent.com/84059211/212465902-0a649d0d-e2eb-434d-9bd8-ad36b0fb775a.png)

<br/>

### Naming rule & Security Group
```
보안 강화를 위한 well-known port 변경
1. ssh 프로토콜 : 22 -> 22222
2. DB 포트 : 3306 -> 3333
```
![image](https://user-images.githubusercontent.com/84059211/212465497-3889ddff-b421-4b1c-8931-48de66aebf0c.png)
![image](https://user-images.githubusercontent.com/84059211/212465556-3d114e6b-c45c-4135-beba-32e43cd1f1bd.png)
![image](https://user-images.githubusercontent.com/84059211/212465566-1623f325-898a-4f33-801b-848f80f2aa94.png)
![image](https://user-images.githubusercontent.com/84059211/212465692-b8a169c7-633e-48a5-947c-7db5452bdc29.png)

<br/>

### Crontab을 통한 서버 체크 및 로그 관리
```
1. 서비스 상태 체크 스크립트 및 로그 관리용 스크립트 작성
2. 두 스크립트는 Crontab에 설정하여 자동 관리
```
![image](https://user-images.githubusercontent.com/84059211/212465616-41c4504c-d263-4d42-9544-0f6dc6273421.png)

<br/>

### Auto Scaling용 WAS 로그 관리
```
언제 종료될지 알 수 없는 Autoscaling된 서버의 상태를 고려하여, 서버 Shutdown시 로그가 전송되도록 설정
```
![image](https://user-images.githubusercontent.com/84059211/212465673-9fd0118f-8543-4163-988a-b4ebb628e6c4.png)

<br/><br/>
***

<div align=center>
<h4> 👈 back to main 👈 </h4>
<a href="https://github.com/bbyu2"> 
<img src="https://img.shields.io/endpoint?label=bbyu2&logo=github&style=for-the-badge&url=https%3A%2F%2Fgithub.com%2Fbbyu2%2F"/>
</a>
</div>
