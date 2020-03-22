Todo list
使用node框架，构建一个Restful API，能够完成Todo list的以下功能。
返回所有Todo任务
创建一个新的Todo任务
返回一个指定ID的Todo任务
删除一个Todo任务
为简化流程，不引入数据存储，即，不需要做数据持久化，可以在服务器运行时满足功能即可。
Todo中一个任务的JSON格式定义为：
  {
    "id": 1,
    "content": "Restful API homework",
    "createdTime": "2019-05-15T00:00:00Z"
  }
进一步的功能提示：需完成的四个功能的Restful API定义如下，实现即可。
GET /api/tasks/
POST /api/tasks/
GET /api/tasks/{id}
DELETE /api/tasks/{id}


# Prerequirement
- vscode
- node
    - by nvm: https://github.com/nvm-sh/nvm
- postman
    - See: https://www.postman.com/
- bash
    - Linux/Mac: zsh, See: https://www.zsh.org/
    - Windows: Git Bash

# Initialize the project
```shell
mkdir crud
cd crud
npm init -y
npm install --save express --registry=https://registry.npm.taobao.org
npm install --save-dev nodemon --registry=https://registry.npm.taobao.org
npm install --save-dev mocha --registry=https://registry.npm.taobao.org
npm install --save-dev supertest --registry=https://registry.npm.taobao.org
mkdir src
# touch src/app.js
```

# Try the example
## 1. See https://expressjs.com/en/starter/hello-world.html
```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => res.send('Hello World!'))

app.listen(port, () => console.log(`Example app listening on port ${port}!`))
```
## 2. Run the app.js by nodemon
Add a scirpt in the `package.json`:
```
  "scripts": {
    "start": "nodemon ./src/app.js",
    "debug": "DEBUG=express:* nodemon ./src/app.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
```
Then run the following command in shell:
```shell
npm run debug
```
or
```shell
npm run start
```
## 3. Test by postman
