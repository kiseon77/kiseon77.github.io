---
title : 홈서버에 배포한 프로젝트 클라우드 플레어에서 도메인 달기
date : 2025-08-25 18:07:00 +09:00
categories : [tailwind]
tags : [tailwind , css] 
---

# 저의 효도 프로젝트 unisize에게 드디어 이름이 생겼어요.
<img width="996" height="1458" alt="Image" src="https://github.com/user-attachments/assets/beb95803-6ba6-42e8-ba63-00fa7cbb997b" />

## 도메인부터 냅다 사버리기

<img width="2038" height="890" alt="Image" src="https://github.com/user-attachments/assets/6948b2c1-3e5c-4860-b32b-4120efd2584d" />
클라우드 플레어 가입하고, 간지나보이는 도메인으로 바로 사버렸다

### [트러블슈팅01] 냅다 배포 금지
<img width="1435" height="806" alt="Image" src="https://github.com/user-attachments/assets/106c2f5a-4b58-42bd-91b3-6cd36cbbca1a" />
먼저 내 프로젝트는 프론트와 백 모두 홈서버에 1차 배포가 되어있다.
도메인을 사고 흐름따라 깃허브 레포 연결하고, 진행하다보면 vercel올리듯이 배포가 되는데
개인적인 프로젝트면 아주 편했겠지만 나는 홈서버에 배포된 아이를 배포해야하기 때문에 다급히 빌드 취소를 눌러줬다

## 터널링하기

<img width="1435" height="806" alt="Image" src="https://github.com/user-attachments/assets/d5bc538f-d217-46ad-bc13-583062d1a1b9" />
1. https://one.dash.cloudflare.com/ 에서 우선 터널부터 생성해줬다.
2. 터널이름을 지어주고
3. 홈서버에 클라우드플레어를 설치해주었다
<br/><img width="718" height="356" alt="Image" src="https://github.com/user-attachments/assets/8efb8d1f-547d-41c1-885e-8ed5de9c2510" />

### [트러블슈팅02] 어,,? cname, a, aaaa 네? www 안된다고요? 뭐가 권장인데요..?

분명 정처기 필기하고, 취업 전에 cs공부하면서 공부했을 dns,, 막상 적용하려고 보니 뭐가 뭔지 일도 모르겠더군요..
불안한 마음에 *(와일드카드)도 해보고 cname, a해서 중복으로 dns지정하려다가 실패하고,,
1시간의 사투 끝에 기존에 이것저것 지정한 dns지워버리고 하위도메인에 www 지정하고 끝나버린 상황에 대해서
아주 즐거웠습니다. <br/> <br/>
[DNS란](https://www.cloudflare.com/ko-kr/learning/dns/what-is-dns/) 여기 보면서 공부하고, 단어가 단어의 꼬리를 물어서 공부하고, 이번 기회에 프론트엔드 개발자로서 네트워크도 공부해야겠다는 생각이..!!
<img width="2086" height="1370" alt="Image" src="https://github.com/user-attachments/assets/d4bcab8b-b7ec-4a45-845d-1c8b7b5d70f1" />
## 여튼 잘 올라갔다
홈서버 ip주소로 들어가지 않아도 이제 어디든 마음대로 보여줄 수 있다는게 행복아니겠습니까
 <br/> 마치 초등학생이 된 자식을 본 마음으로 이제 이것저것 사주듯이 보안적으로도 어떻게 할 수 있을지 고민도 해보고  <br/> 클라우드플레어, 터널링, dns를 잘 몰랐던 수치를 잊어버리기 위해 공부도 하고  <br/> 매일 작업하고 있으니깐 블로그도 잘 써봅시다