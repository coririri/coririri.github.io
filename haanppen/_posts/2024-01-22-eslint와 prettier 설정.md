---
layout: post
title: "eslint와 prettier 설정"
date: 2024-01-22 21:02:24 +0900
categories: haanppen
---

# eslint와 prettier 설정

둘다 코드 컨벤션을 맞춰 유지보수 및 협업을 용이하게 해주기 위한 도구들이다.

## eslint와 prettier의 차이점

eslint는 코드가 관습에서 벗어나면 경고 메시지를 띄워주는 용도이고, prettier는 코드가 관습에서 벗어나면 포맷팅을 통해 수정을 해주는 도구이다. (둘다 오류가 발생하면 프로젝트 build가 실패한다.)

## eslint와 prettier의 충돌과 해결방법

둘다 코드 컨벤션을 두는 기준이 다르기 때문에, 서로 충돌하는 관습이 생길 수 있고, 이를 해결 하기 위해 prettier 홈페이지에서 해결방법을 제시한다

1. Prettier와 충돌하는 ESLint 규칙들을 꺼주는 eslint-config-prettier
2. Prettier를 ESLint 규칙으로 실행시켜주는 eslint-plugin-prettier
3. Prettier를 실행한 직후 ESLint를 실행시켜주는 prettier-eslint
   1번의 방법이 권장된다.

### Prettier & eslint-config-prettier 설치 및 설정

1. 설치: npm i -D prettier eslint-config-prettier
2. 루트 폴더 위치에 .prettierrc 파일 (prettier 설정 파일)을 생성합니다.
3. [prettier옵션](https://prettier.io/docs/en/options.html)을 참고해 .prettierrc 파일에 작성

```json
{
  // 쌍따옴표 대신 홑따옴표 사용
  "singleQuote": true,
  // 모든 구문 끝에 세미콜론 출력
  "semi": true,
  // 탭 대신 공백으로 들여쓰기
  "useTabs": false,
  // 들여쓰기 공백 수
  "tabWidth": 2,
  // 가능하면 후행 쉼표 사용
  "trailingComma": "all",
  // 줄 바꿈할 길이
  "printWidth": 80,
  // 객체 괄호에 공백 삽입
  "bracketSpacing": true,
  // 항상 화살표 함수의 매개 변수를 괄호로 감쌈
  "arrowParens": "always",
  // OS에 따른 코드라인 끝 처리 방식 사용
  "endOfLine": "auto"
}
```

### eslint 설치 및 설정

1. 설치: npm install eslint --save-dev
2. npx eslint --init를 통해 환경 세팅
3. 환경 세팅 시 질문과 답변

- How would you like to use ESLint?  
  To check syntax, find problems, and enforce code style
- What type of modules does your project use?  
  CommonJS와 ES modules 중 선호하는 모듈 시스템을 선택
- Which framework does your project use?  
  프로젝트가 사용하고 있는 프레임워크를 선택
- Does your project use TypeScript?  
  프로젝트가 TypeScript를 사용하는지 여부를 선택
- Where does your code run?  
  Browser와 Node 중 코드가 실행되는 환경을 선택 (우아한테크코스 미션들의 실행 환경은 Node, 중복 선택도 가능)
- How would you like to define a style for your project?  
  Use a popular style guide
- Which style guide do you want to follow?  
  선호하는 스타일 가이드 선택 (우아한테크코스의 자바스크립트 스타일 가이드 기준은 Airbnb)
- What format do you want your config file to be in?  
  JavaScript, YAML, JSON 중 선호하는 설정 파일의 포맷을 선택
- Would you like to install them now? (peerDependencies 설치)  
  Yes
- Which package manager do you want to use?  
  npm, yarn, pnpm 중 선호하는 패키지 매니저를 선택

4. .eslintrc.js
   루트에 .eslintrc.js파일이 생성 되었다.

```js
extends: ['airbnb-base', 'prettier']
```

prettier가 마지막에 가서 eslint-config-prettier가 eslint 설정을 덮어쓰이도록 한다.

### VSCODE의 EXTENSION 설치

prettier module은 formatting을 진행할 때 precommit이나 복잡한 방법들을 사용하기 때문에, extension의 도움을 받아 저장 시 수정하는 방법이 가장 깔끔하다.

1. ESLint와 Prettier 확장 프로그램을 설치
2. VSCode의 setting.json 파일에 아래 내용을 작성합니다.

```json
// 파일을 저장할 때마다 `eslint` 규칙에 따라 자동으로 코드를 수정
"editor.codeActionsOnSave": { "source.fixAll.eslint": true },
// `prettier`를 기본 포맷터로 지정
"editor.defaultFormatter": "esbenp.prettier-vscode",
// 파일을 저장할 때마다 포매팅 실행
"editor.formatOnSave": true,
```

### eslint 설정 파일에 대해서 자세히 알아보자

https://eslint.org/docs/latest/use/configure/
