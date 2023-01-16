# 코인거래소 ABCbit 3Tier Architecture 구축

# 목차
[1. 개요](#개요)

[2. 메인 구축 과정](#메인-구축-과정)

<br/>

## 개요
#### - CSP : AWS
#### - 스프링 오픈 소스를 활용한 3Tier구축
#### - 고가용성 및 부하분산을 위한 Web, WAS(Web Application Server), DB분리
#### - 보안 및 웹 페이지의 안정성을 위한 세션 클러스터링, Crontab을 활용한 로그 관리, CDN(Content Delivery Network)기능 추가


### 구축 인원 및 기간
- 기간 : 2022-08-29 ~ 2022-09-16(총 3주)
- 인원 : 5명(인프라 구축 5명)

### 구축환경
```
1. Notion, Slack, Google 서비스를 활용한 협업
2. AWS의 서비스를 기반으로 터미널 프로그램(MobaXterm, Putty, Xshell)을 이용한 서버 접속, Spring프로젝트 운영 관리
```
![image](https://user-images.githubusercontent.com/84059211/212465172-da9c20cc-e6ef-4f57-aff9-c002b8db74fa.png)

### 시장 분석
```
1. 많은 금융 기업들이 온프레미스 환경에서 클라우드 환경으로 옮김
2. ABCbit 또한, 아래와 같은 이유로 클라우드 환경을 선택
```
![image](https://user-images.githubusercontent.com/84059211/212464910-5fef4c1d-de15-4eb6-9bd9-7d36374e12c0.png)


### 고객 요구사항 및 대응 방안
![image](https://user-images.githubusercontent.com/84059211/212464883-c92f3f0c-bd87-4922-8d7e-f7a8b5a00e92.png)
![image](https://user-images.githubusercontent.com/84059211/212464891-24f99dfe-45d7-4871-8445-09e41cc27152.png)

<br/>

## 메인 구축 과정
### Solution Architecture
![image](https://user-images.githubusercontent.com/84059211/212464998-2c844cef-1be6-455d-837b-d77c7e6cd237.png)

### ABCbit Service
```
[참고] https://github.com/spring-projects/spring-petclinic
스프링 예제 펫클리닉을 활용한 웹서비스 구축
```
![image](https://user-images.githubusercontent.com/84059211/212465902-0a649d0d-e2eb-434d-9bd8-ad36b0fb775a.png)


### Naming rule & Security Group
```
보안 강화를 위한 well-known port변경후, 사용
```
![image](https://user-images.githubusercontent.com/84059211/212465497-3889ddff-b421-4b1c-8931-48de66aebf0c.png)
![image](https://user-images.githubusercontent.com/84059211/212465556-3d114e6b-c45c-4135-beba-32e43cd1f1bd.png)
![image](https://user-images.githubusercontent.com/84059211/212465566-1623f325-898a-4f33-801b-848f80f2aa94.png)
![image](https://user-images.githubusercontent.com/84059211/212465692-b8a169c7-633e-48a5-947c-7db5452bdc29.png)

### Crontab을 통한 서버 체크 및 로그 관리
![image](https://user-images.githubusercontent.com/84059211/212465616-41c4504c-d263-4d42-9544-0f6dc6273421.png)

### Auto Scaling용 WAS 로그 관리
![image](https://user-images.githubusercontent.com/84059211/212465673-9fd0118f-8543-4163-988a-b4ebb628e6c4.png)
