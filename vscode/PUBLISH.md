# VSCODE插件打包、发布

## 1. 本地打包
安装vsce打包工具：
``` js
npm i vsce -g
```
打包
``` js
vsce package
```
打包的时候如果没有设置git repository会有提示，所以最好设置一下。不设置也没有关系。

## 2. 发布前准备
    2.1 [注册Microsoft账号](https://login.live.com/)

    2.2 [用Microsoft账号登录Azure](https://aka.ms/SignupAzureDevOps)

    2.3 点击创建新的个人访问令牌，这里特别要注意 **Organization** 要选择all accessible organizations，Scopes要选择Full access，否则后面发布会失败。并复制令牌，记住令牌，令牌创建后不能再次看见，只能重置掉。

    2.4 创建发布账号
    ``` js
    vsce create-publisher your-publisher-name
    ```
    2.5 登录发布账号
    ``` js 
    vsce login your-publisher-name
    ```

## 3. 发布
``` js
vsce publish
```
**增量发布**
``` js
vsce publish minor
```
**取消发布**
``` js 
vsce unpublish (publisher name).(extension name)
```