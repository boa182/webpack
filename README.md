# 学习webpack
> 记录个人在学习和工作运用中的小坑小洼，以及如何越过的

## npm run build 常见坑
1.**Failed to load resource: net::ERR_FILE_NOT_FOUND或者vue dist文件下的index.html没显示**
```
解决办法：
  在webpack.base.conf.js里
    publicPath: process.env.NODE_ENV === 'production'
      ? './' +config.build.assetsPublicPath
      : './' + config.dev.assetsPublicPath
  还不行？
  index.js 里面的build的
    assetsPublicPath: '/vue-admin/' 改为'/' 。
```