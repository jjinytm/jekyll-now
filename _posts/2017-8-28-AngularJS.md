---
layout: page
title: AngularJS
category: javascript
---

- AngularJS 란?
AngularJS는 자바스크립트 Framework다.
강력한 데이터 바인딩
백엔드 통합 서비스 내장

- Framework 란?
[소프트웨어 Application이나 솔루션의 개발을 수월하게 하기 위해 소프트웨어의 구체적 기능들에 해당하는 부분의 설계와 구현을 재사용 가능하도록 협업화 된 형태로 제공하는 소프트웨어 환경을 말한다.]

AngularJS 2.0
* 빠른 구축이 가능하다.
* 새로운 기능들을 사용할 수 있다.(using new features - classes, object)
* 간결해진 API
* 개선된 생산성

AngularJS 에서 component란?
Template + Class(propertis, method 포함) + Metadata
: 템플릿(Template)은 앵귤러 프레임워크가 HTML을 템플릿으로 간주하여 1차적으로 앵귤러 구문을 해석하고
 데이터를 바인딩하는 템플릿 해석기 역할을 한다.

: 지시자(Directive) 는 HTML을 확장하는 앵귤러만의 가장 특별한 기능으로 HTML 태그로서 뷰를 확장할 수 있고,
  그 안에 상태와 액션을 담아 컴포넌트화 할 수 있으므로 화면 개발의 생산성을 높여준다.


1) Template
View layout
* HTML의 형태로 작성된다.
* 바인딩(Binding)과 지시자(Directive)를 포함한다.

2) class
* Properties 와  Method 를 포함할 수 있다.
	- Properties  : data
	- Method  : logic
* Code supporting the view
* 타입스크립트(TypeScript) 형태로 작성된다.

3) Metadata
* Angular에 대한 추가 데이터
* Decorator로 정의한다.

<b>ngFor 기능</b>
ngFor는 템플릿 중 특정 내용이나 형태를 반복해야 할 때 사용하며 '<li>'형태로 리스트를 작성하는 경우에 유용하다.
리스트형태의 표현을 해야하는 경우 사용하면 좋다.

```javascript
@Component({
	selector: 'my-app',
	template: ` <h1>{{title}}</h1>
						  <h2>Member</h2>
								<ul class="heroes">
									<li *ngFor="let hero of heroes"> {{hero}} </li>
									<li *ngFor="let hero of heroes2"> {{hero}} </li>
								<ul> `
})
export class AppComponent {
	title = '1llionaire Recode';
	heroes = ["zico", "jlee", "nas"];
	heroes2 = ["Beenzino", "The Quite", "Dok2"];
	myHero = this.heroes[0];
}
```
