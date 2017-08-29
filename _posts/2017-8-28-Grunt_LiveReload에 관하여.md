---
layout: page
title: Grunt_LiveReload에 관하여
category: javascript
---

웹 어플리케이션을 개발하다보면 수정내역에 대한 확인을 위해 수차례 웹 페이지를 새로고침해야 될 때가 있다.
아무리 간단한 수정이라도 페이지를 새로고침하기 위해 F5버튼을 쉴새없이 클릭해야 한다.
Grunt와 Watch를 사용하여 어플리케이션이 수정되었을때 자동으로 페이지를 새로고침하는 방법을 알아보자.

Grunt 환경은 Gruntfile.js file내에 구성되어 있다.

Watch 설치가 필요하다.
Watch는 파일내용의 변경을 감지하는 플러그인이다.

Gruntfile.js내에 아래와 같이 작성한다.

```javascript
module.exports = function(grunt){
	grunt.initConfig({
		pkg:grunt.file.readJSON('package.json'),

		watch:{
			files:['public/**','server/**'],
			tasks:''
		},
	});

	grunt.loadNpmTasks('grunt-contrib-watch');
};
```

cmd에서 'grunt watch'를 실행하고 파일을 변경하면 프롬프트창에서 다음과 같은 메시지를 볼수가 있다.

```javascript
grunt watch
Running "watch" task
Waiting...
>> File "public\js\app.js" changed.
Completed in 0.000s at Fri Mar 27 2015 17:29:16 GMT+0100 (W. Europe Standard Time) - Waiting...
```

이와 같은 메시지가 뜬다면 watch 설치 및 설정이 제대로 되어있다는 것을 알 수 있다.
하지만, 파일이 언제 변경되었는지 알려고 하는것이 아니다.
정말 필요한것은 파일변경이 일어났을때 브라우저가 자동으로 페이지를 새로고침하고, 변경된 내용을 보여주는 것이다.

<h3>Livereload</h3>
Livereload기능을 사용하기 전에 grunt-express 모듈의 설치가 필요하다.

```javascript
//grunt-contrib-express가 아니라 grunt-express 다. 유의하자.
npm install grunt-express --save
```

grunt-express모듈은 신속하게 서버를 구동시키는 기능을 제공하여 주며, 몇가지 멋진 기능을 포함하고 있다.
그 멋진 기능중에 하나가 바로 Livereload 기능이다.
Watch모듈이 파일의 변경을 감지하면 Livereload 모듈이 페이지를 자동으로 새로고침하여 준다.
이 기능들이 제대로 동작하려면 Gruntfile.js 파일 내에 아래와 같이 작성해주어야 한다.

```javascript
module.exports = function(grunt){
	grunt.initConfig({
		pkg:grunt.file.readJSON('package.json'),

		watch:{
			options:{livereload:true},
			files:['public/**','server/**'],
			tasks:[]
		},
  		express:{
  			all:{
  				options:{
  					port:3000,
  					hostname:'localhost',
  					bases:['./public'],
  					livereload:true
  				}
  			}
  		}
	});

	grunt.loadNpmTasks('grunt-contrib-watch');
	grunt.loadNpmTasks('grunt-express');
	grunt.registerTask('server',['express','watch']);

};
```

이제 cmd창에 다음과 같은 명령어로 서버를 실행하여 보자.
```javascript
grunt server
```

파일의 변경이 일어났을때 웹페이지가 자동으로 새로고침되어 변경내용이 반영된것을 볼 수 있다.
