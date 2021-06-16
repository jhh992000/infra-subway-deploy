<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-%3E%3D%205.5.0-blue">
  <img alt="node" src="https://img.shields.io/badge/node-%3E%3D%209.3.0-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/next-step/atdd-subway-service">
</p>

<br>

# 인프라공방 샘플 서비스 - 지하철 노선도

<br>

## 🚀 Getting Started

### Install
#### npm 설치
```
cd frontend
npm install
```
> `frontend` 디렉토리에서 수행해야 합니다.

### Usage
#### webpack server 구동
```
npm run dev
```
#### application 구동
```
./gradlew clean build
```
<br>

## 미션

* 미션 진행 후에 아래 질문의 답을 README.md 파일에 작성하여 PR을 보내주세요.

### 1단계 - 망 구성하기
1. 구성한 망의 서브넷 대역을 알려주세요
- 대역 : 192.168.100.0/24
  - 관리용 서브넷 : 192.168.100.0/27, (AZ: ap-northeast-2c, IGW)
  - 내부망 서브넷 : 192.168.100.32/27, (AZ: ap-northeast-2a, NT)
  - 외부망1 서브넷 : 192.168.100.64/26, (AZ: ap-northeast-2c, IGW)
  - 외부망2 서브넷 : 192.168.100.128/26, (AZ: ap-northeast-2a, IGW)

2. 배포한 서비스의 공인 IP(혹은 URL)를 알려주세요

- URL : http://jhh992000.ddns.net:8080

3. 베스천 서버에 접속을 위한 pem키는 [구글드라이브](https://drive.google.com/drive/folders/1dZiCUwNeH1LMglp8dyTqqsL1b2yBnzd1?usp=sharing)에 업로드해주세요

---

### 2단계 - 배포하기
1. TLS가 적용된 URL을 알려주세요
   - URL : https://jhh992000.ddns.net

2. 설정파일 나누기
   - git submodule 을 활용하여 설정외부화
   - https://github.com/jhh992000/infra-subway-config (확인을 위해 public repository 로 설정)
  
3. 데이터베이스 스키마 버전관리
   - src/main/resources/db/migration/V1__init.sql
   - src/main/resources/db/migration/V2__member_add_name.sql