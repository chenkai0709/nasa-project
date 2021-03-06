# NASA Mission Control
> 利用[SpaceX](https://github.com/r-spacex/SpaceX-API/tree/master/docs#rspacex-api-docs)公開資料，製作一個太空任務管理平台  

> 此為[課程](https://www.udemy.com/course/complete-nodejs-developer-zero-to-mastery/)練習專案  


![image](https://github.com/chenkai0709/nasa-project/blob/52f7d5a1fc6b56e7dead382593239a49088902e4/nasa-project.png)  
  
## Features
- 使用框架
  - 前端: React
  - 後端: Node.js + Express
  - Database: MongoDB Atlas
  - ODM(ORM): Mongoose
- 串接 [SpaceX Api](https://github.com/r-spacex/SpaceX-API/tree/master/docs#rspacex-api-docs) 取得相關資料
- 使用 [SuperTest](https://www.npmjs.com/package/supertest) 連接 mondoDB Altas 進行 API Test
- 使用 node cluster 進行效能優化並利用 pm2 tool 管理
- 使用 GitHub Action 進行 CI/CD，並部屬至AWS EC2

## AWS/Docker
- Docker:  [docker image](https://hub.docker.com/r/chenkaiii/nasa-project)
```Bash
docker pull chenkaiii/nasa-project
```
- AWS:  [AWS部屬網站](http://3.94.82.91:8000/)

## 環境依賴
node v12.19.0+

## 指令列表
1. 新增系統環境變數  
  PORT        // ex: 8000  
  MONGO_URL   // your mongoDB url

2. `npm run install`        - 安裝node執行環境

3. `npm run watch`          - 執行開發模式 (enable node live server)

4. `npm run test`           - 執行API Test

5. `npm run deploy`         - 執行前後端編譯

6. `npm run deploy-cluster` - 執行cluster模式編譯

## 目錄結構描述
```
├── Readme.md                   // help
├── client                      // 前端放置目錄
├── server                      // 後端放置目錄
│   ├── data                    // spaceX 資料
│   ├── src                     // 開發環境
│   │   ├── models              // data 資料結構
│   │   ├── routes              // controllers / routes
│   │   ├── services            // 共用service (mongoose & pagination)
│   │   ├── app.js              // express
│   │   └── server.js           // server 起始位置
│   ├── package.json            
│   └── .gitignore
├── .github
│   └── workflows               // gitHub action
├── Dockerfile
├── .dockerignore
└── package.json
```