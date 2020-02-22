---
title:  "NodeJs - 5. WebServer"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - WebServer
last_modified_at: 2020-02-22T09:06:00-05:00
---
# 

## 미들웨어

    
    npm install express --save

### **static 미들웨어**

    
    npm install server-static ---save

    
    app.use(express.static(path.join(__dirname, 'public')));

### **body-parser 미들웨어**

    
    npm install body-parser --save

    app.use(bodyParser.json()); // application/json 형식으로 전달된 요청 파라미터를 파싱.

    
    app.use(bodyParser.urlencoded({ extended: true })); // application/x-www-form-urlencoded 형식으로 전달된 요청 파라미터를 파싱.

**Router 미들웨어**

    
    // app.js
    var router = express.Router();
    .....
    router.route('process/login:name').post('function(req,res) {
    ....
    });
    app.use('/'.router);

    //html.html
    
    <form method="post" action="/process/login/boy">
    
    // 등록되지 않은 패스에 대해 페이지 오류 응답
    app.all('*', function(req, res) { res.send(404, '<h1> 페이지를 찾을 수 없음돠. </h1>'); });

### **express-error-handler 미들웨어**

    
    npm install express-error-handler --save

    // code
    var expressErrorHandler = require('express-error-handler');
    ....
    
    var errorHandler = expressErrorHandler({ static: { '404': './public/html/404.html' }
    });
    
    app.use(expressErrorHandler.httpError(404) );
    
    app.use(errorHandler);
    
    ....

### **Using Token**

    
    // code
    var router = express.Router();
    
    .....
    
    router.route('process/users/:id').get('function(req,res) {
    
    var paramId = req.params.id; console.log('/process/usersdhk 토큰 %s를 사용해 처리함', 
    
    paramId); res.writeHead('200', {'Content-Type':'text/html;charset=utf8'}); res.write('<h1> Express 서버에서 응답한 결과입니다.</h1>'); res.write('<div><p>Param Id:'+paramId+'</p>
    
    </div>'); res.end();
    
    });
    
    app.use('/'.router);