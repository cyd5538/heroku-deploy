배포 연습
client, server 폴더로 나눈후에
client에서 빌드해서 server 폴더로 

이렇게 적어줘야 빌드안에 있는 파일이 적용됨
const path = require('path');
app.use(express.static(path.join(__dirname, '/build')));

app.get('/', function (req, res) {
    res.sendFile(path.join(__dirname, '/build/index.html'));
});


client build > build 폴더 server로  > 서버 실행

client 폴더로 이동
npm ci
npm run build
client/build > server/build 폴더로 이동

server 폴더로 이동 
npm ci
node app.js


루트 package.json에 넣기
  "heroku-prebuild": "cd client && npm ci && npm run build && mv build ../server",
  "start": "cd server && npm ci && node server.js",
