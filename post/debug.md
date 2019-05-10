
通过debug packages 调试

## ENV

- env: env-wsl
- os: ubuntu16

## STEP

### debug package 

如果用了debug这个包的就可以, 在环境变量加 DEBUG=**packagesName 情况下 ，那么 node 程序中，会覆盖原来的 DEBUG 值,从而多输出一些信息

比如在 https://github.com/eiuapp/tl-lvchuang-src-server 中的 ./lib/infoSql.js 用了一个包 debug

`set DEBUG=infoSql` 或者 `export DEBUG=infoSql` ，再 `node index.js` 

```javascript
var debug = require('debug')('infoSql')
```

那么就可以在 pm2 logs 中看到 debug 的 sql 

```
16|index  | Fri, 10 May 2019 10:23:40 GMT infoSql SELECT count(*) as number, area as type FROM enterprise_data GROUP BY area
16|index  | Fri, 10 May 2019 10:23:40 GMT infoSql []
```




### 问题(已解决) ###
### 问题(未解决) ###
