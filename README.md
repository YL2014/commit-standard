### 规范commit


#### 环境配置

- 使用angular团队的preset
```
$ yarn global add commitizen cz-conventional-changelog
echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc
```

- 自定义
```
$ yarn global add commitizen cz-customizable
echo '{ "path": "cz-customizable" }' > ~/.czrc
```
自定义方法需copy `.cz-config.js`到项目的任何地方

#### 添加commitlint

- 使用angular团队的
```
$ yarn add @commitlint/config-conventional @commitlint/cli -D

# 项目目录下添加.commitlintrc.js，内容如下

module.exports = {
  extends: [
    '@commitlint/config-conventional'
  ],
  rules: {}
}
```

- 自定义
```
$ yarn add commitlint-config-cz @commitlint/cli -D

# 项目目录下添加.commitlintrc.js，内容如下

module.exports = {
  extends: [
    'cz'
  ],
  rules: {}
}
```

#### 结合Husky

```
$ yarn add husky@next -D

# package.json 中添加

"husky": {
  "hooks": {
    "commit-msg": "commitlint -e $GIT_PARAMS"
  }
},
```

#### standard-version
```
$ yarn add standard-version -D

# package.json 中添加

"scirpt": {
  "release": "standard-version"
}
```

### 参考
- [https://juejin.im/post/5afc5242f265da0b7f44bee4](https://juejin.im/post/5afc5242f265da0b7f44bee4)
- [https://gist.github.com/leohxj/7bc928f60bfa46a3856ddf7c0f91ab98](https://gist.github.com/leohxj/7bc928f60bfa46a3856ddf7c0f91ab98)
- [husky](https://github.com/typicode/husky)
- [commitlint](https://github.com/marionebl/commitlint)
- [cz-customizable](https://github.com/leonardoanalista/cz-customizable)





