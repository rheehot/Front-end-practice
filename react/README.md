# 2020.10.21

1. `webpack-dev-server` 실행되지 않는 이유을 찾아야 합니다.
1. `npx create-react-app {디렉터리}`의 react 프로젝트가 많이 사용되는지 확인해야 합니다.

# 2020.10.22

1. react webpack 후 파일 실행 시 발생하는 에러는 ```process.env.NODE_ENV``` 환경변수값이 undefined이라서 생기는 문제이다.
   - ```webpack --mode=production```으로 값은 전달해주면 된다.
1. webpack-cli가 버전업이 되면서 더이상 ```webpack-dev-server``` 커맨드가 먹지 않는 이슈가 있었다.
   - ```webpack serve```으로 호출하면 된다
1. 하지만 위와같이 호출해도 똑같이 환경변수에 대한 문제가 발생한다
   - ```webpack serve --mode development --env development```으로 해결한다

## devDependencies

```json
"devDependencies": {
    "@babel/core": "^7.12.3",
    "@babel/preset-env": "^7.12.1",
    "@babel/preset-react": "^7.12.1",
    "babel-loader": "^8.1.0",
    "clean-webpack-plugin": "^3.0.0",
    "css-loader": "^5.0.0",
    "html-loader": "^1.3.2",
    "html-webpack-plugin": "^4.5.0",
    "mini-css-extract-plugin": "^1.1.1",
    "node-sass": "^4.14.1",
    "react": "^17.0.0",
    "react-dom": "^17.0.0",
    "sass-loader": "^10.0.3",
    "style-loader": "^2.0.0",
    "webpack": "^5.1.3",
    "webpack-cli": "^4.1.0",
    "webpack-dev-server": "^3.11.0"
  }
```

## 참조

- [트러블 슈팅에 대한 힌트를 제공](https://stackoverflow.com/questions/59611597/error-cannot-find-module-webpack-cli-bin-config-yargs)
- [해당 문제 이슈 목록 이걸 보고 해결함](https://github.com/webpack/webpack-dev-server/issues/2759)
- [가이드](https://velog.io/@jeff0720/React-%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD%EC%9D%84-%EA%B5%AC%EC%B6%95%ED%95%98%EB%A9%B4%EC%84%9C-%EB%B0%B0%EC%9A%B0%EB%8A%94-Webpack-%EA%B8%B0%EC%B4%88)