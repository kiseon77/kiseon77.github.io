---
title : 개발자라면 알아야하는 Tailwind Font 적용기
date : 2025-08-25 18:07:00 +09:00
categories : [tailwind]
tags : [tailwind , css] 
---


# font 관리 어떻게 하세요?
회사 프로젝트 오픈일이 얼마 안남았다. 그래서 그런지 폰트 하나로도 한시간동안 회의에서 이야기 하는 시기가 와버렸다.<br/> 기본 폰트를 전체적으로 적용하되, 일부 페이지에서는 다른 폰트를 사용하고 있어서 전체적으로 3개의 폰트를 사용하고 있다. <br/> 이 프로젝트의 히스토리를 따라가보자면 기본 폰트가 2번 정도 바뀌었다. <br/><br/>
대표님이 배포된 내용을 보던 중, 일부 폰트들이 너무 달라서 회의시간에 기본 폰트가 적용되어있지 않은 부분을 찾기 시작했다.

<br/>해외에 계시는 대표님 컴퓨터에서는 노트북 기본 폰트가 보이지만, 한국에 있는 우리들에겐 기본 폰트로 적용되어있음을 확인했다. <br/> 회사의 프리랜서 프론트엔드 시니어 개발자님계서 글로벌 CSS를 손봐주시기로 했다.

## 폰트 두께가 다 깨져버렸어요
시니어 개발자님께서 일부로 폰트를 지정하지 않으면 기본 폰트가 적용될 수 있도록 세팅해주시고 브랜치에 올려주셨다.
<br/><br/>
어.. 제 화면에서 테일윈드로 두께 적용한게 다 깨져버렸다
<br/>어디는 스타일에 기본폰트를 폰트 패밀리로 지정해서 사용하고, 어디는 인라인 스타일로 폰트를 지정해서 사용하고 있었다.
<br/><br/>
내가 작업한 부분만 깨져버리니 내가 뭘 잘못했는지 찾아보기로했다.

## 폰트 CSS
초반 css 폰트 세팅할때 두께별로 폰트를 따로 가져오고, class를 지정해서 두께를 지정할때 클래스를 주는 형태로 세팅 되어있었다.
<br/>
그렇게 되면서 font-family를 두께에 맞춰 각각 이름을 지정해주었다.
```
@font-face {
  font-family: "Pretendard-SemiBold";
  src: url("/fonts/Pretendard-SemiBold.woff") format("woff");
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: "Pretendard-Bold";
  src: url("/fonts/Pretendard-Bold.woff") format("woff");
Black  font-weight: 400;
  font-style: normal;
}

.pretendard-SemiBold {
	font-family: 'Pretendard-SemiBold';
	font-weight: 500;
	font-style: normal;
}

.pretendard-Black {
	font-family: 'Pretendard-Black';
	font-weight: 900;
	font-style: normal;
}
```
![image](https://github.com/user-attachments/assets/c955b933-fadf-47e1-8b4e-84a5a9827028)

초기엔 font-family도 달랐지만, @font-face에서 font-weight를 400으로만 불러왔기 때문에 
<br/>css에서 지정해준 font-weight와 맞지 않아서 fallback으로 비슷한걸 찾아서 두께를 적용해주던가,<br/>이미지처럼 두께가 적용되지 않은 상태로 보여진다.

### 그렇다면 font 어떻게 적용해야할까?
우선 font-family부터 통일해주어야한다. <br/>그래야지 css가 해당 폰트에서 우선적으로 알맞은 두께를 찾을것이다.
<br/><br/>
그리고 실제 두께에 맞는 font-weight를 지정해준다.<br/>이렇게 하면 Pretendard에서 두께가 500인 것과 900인것을 먼저 찾을 수 있을것이다.
```
@font-face {
  font-family: "Pretendard";
  src: url("/fonts/Pretendard-SemiBold.woff") format("woff");
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: "Pretendard";
  src: url("/fonts/Pretendard-Bold.woff") format("woff");
Black  font-weight: 900;
  font-style: normal;
}

.pretendard-SemiBold {
	font-family: 'Pretendard';
	font-weight: 500;
	font-style: normal;
}

.pretendard-Black {
	font-family: 'Pretendard';
	font-weight: 900;
	font-style: normal;
}
```

## 정리해보자면
위의 상황처럼 폰트를 필요한 두께만 각각 불러와서 사용할 경우, <br/>
동일한 폰트의 font-family는 동일하게, font-weight는 불러올때부터 맞는 숫자로 적어주면 된다. <br/><br/>
W3C CSS Fonts 기준으로 아래와 같이 매핑한다<br/>
Thin(100) < Extra Light(200) < Light(300) < Normal / Regular(400) < Medium(500) < Semi Bold(600) < Bold(700) < Extra Bold(800) < Black(900)
<br/><br/>
물론 Pretendard Variable이 있잖아 라고 생각할 수도 있지만, 폰트를 바꿔 지정하기엔 너무 많은 길을 와버렸다.<br/> 출시 이후 리팩토링의 기회가 생긴다면 다시 한번 더 제안 해봐야겠다.