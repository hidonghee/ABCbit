# 코인거래소 ABCbit 3Tier Architecture 구축

# 목차
[1. 개요](#개요)

[2. 개발환경](#개발환경)

[3. 실행방법](#실행방법)

[4. 구현화면-사용자](#구현화면-사용자)

[5. 구현화면-관리자](#구현화면-관리자)

<br/>

## 개요
#### AWS Cloud 서비스를 활용한 WEB, WAS, DB 3Tier 구축

### 구축 인원 및 기간
- 기간 : 2022-08-29 ~ 2022-09-16
- 인원 : 5명 

### 구축환경
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
![image](https://user-images.githubusercontent.com/84059211/212465497-3889ddff-b421-4b1c-8931-48de66aebf0c.png)
![image](https://user-images.githubusercontent.com/84059211/212465556-3d114e6b-c45c-4135-beba-32e43cd1f1bd.png)
![image](https://user-images.githubusercontent.com/84059211/212465566-1623f325-898a-4f33-801b-848f80f2aa94.png)
![image](https://user-images.githubusercontent.com/84059211/212465692-b8a169c7-633e-48a5-947c-7db5452bdc29.png)

### Crontab을 통한 서버 체크 및 로그 관리
![image](https://user-images.githubusercontent.com/84059211/212465616-41c4504c-d263-4d42-9544-0f6dc6273421.png)

### Auto Scaling용 WAS 로그 관리
![image](https://user-images.githubusercontent.com/84059211/212465673-9fd0118f-8543-4163-988a-b4ebb628e6c4.png)
