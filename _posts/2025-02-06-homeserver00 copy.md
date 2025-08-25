---
title : 홈서버 구축기 00
date : 2025-02-05 18:07:00 +09:00
categories : [homeserver]
tags : [homeserver , unisize] 
---
![image](https://github.com/user-attachments/assets/bf097ce0-801a-4f94-9256-053b5c0d74ff)

# 프로젝트 하나를 얼마나 끄는것인가..
깃허브 블로그를 만들면서 처음 작성한 게시글.. 기억 나는가? <br/>
부모님 가게를 돕기 위해 고객/재고 관리시스템(CRM)을 만들기로 했었다. <br/>
모노레포지토리를 파고, 기획도 하고, 디자인..? 여튼 색이 있는 와이어프레임도 짜고 해봤는데 대차게 실패 <br/>
프로젝트 세팅만 과장 안하고 10번은 한것같다. npm도 쓰고 yarn도 쓰고 react했다가 next했다가, storybook쓰려다가 그냥 scss쓰고, tailwind도 해보고 줒대 없이 시간만 흘러서 벌써 4개월은 지났다.  <br/>
그렇게 손님응대 시즌이 지나가고 재고 관리의 시즌이 돌아왔다.  <br/>

## 홈서버를 구축하기로 했다.
내가 프로젝트를 질질 끌고있는게 느껴졌다. 물론 프론트 1, 백 1의 작은 프로젝트라지만 백엔드 개발자님이 서버를 올리고 스웨거를 주시고 나는 언제 작업할지 모르고 속절없이 aws에서 서버비는 나가고... <br/>
그래서 홈서버를 하나 만들어두기로 했다. <br/>
무슨 관계냐구요? 그냥 음.. 일단 멋있어보였어요 ㅎ  <br/>

## 쇠뿔도 단김에 빼라
당근과 중고나라를 통해서 하루만에 미니서버를 구입해왔다.  <br/>
<img width="384" alt="image" src="https://github.com/user-attachments/assets/b80bb0d6-87e9-4eb7-b011-75a78a7566ee" /><img width="383" alt="image" src="https://github.com/user-attachments/assets/3cf37cc1-4ef3-4d1b-8404-4d6d355707f0" />
<br/> 원래는 당근에서 미니pc 세팅되어있는거 구입하고 ssd는 쿠팡 하려고 했는데 생각보다 비싼게 아닌가? 배송 기간이 긴거는 또 싫어서 양재시민의숲으로 당근하러 가면서 또 중고를 찾아보았다. <br/>
마침 원래 사려던게 sk하이닉스 p41 500mb였는데 누가 1tb 12만원에 올려두셨는데 홀린듯이 연락을 하게 되어버렸다 이말이다.  <br/>
(물론 모든 연락은 남자친구가 해줬다ㅎㅎㅎ..) <br/>
그렇게 7시에 퇴근하고 2시간의 홈서버 하드웨어 대장정이 끝났다.

> cpu Amd 5625u 6core<br/>
Ram 16gb<br/>
ssd 1tb<br/>
총 금액 : 32만원<br/>

### 조립
![image](https://github.com/user-attachments/assets/1f4bad8f-380d-4d47-aec6-a0c1f45349cd)<br/>
![image](https://github.com/user-attachments/assets/795ed513-bcef-4c06-8f92-78de6cff6021)<br/>

하드웨어는 준비되었다.<br/>
이미 윈도우 키가 있다고 해서, 윈도우 위에 버츄얼박스 깔고 거기서 unisize와 이외 자잘한 프로젝트 용 서버를 나눠서 우분투에 올려두려는 계_획이다.
