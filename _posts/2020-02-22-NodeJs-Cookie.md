---
title:  "NodeJs - 6. Cookie"
excerpt: "BackEnd"

categories:
  - BackEnd
tags:
  - BackEnd
  - NodeJs
  - Cookie
last_modified_at: 2020-02-22T10:06:00-05:00
---
# 
사용자가 로그인 상태인지 아닌지 확인하고 싶을 때 쿠키나 세션 사용.

쿠키는 클라이언트 웹 브라우저의 정보,

세션은 웹 서버에 저장되는 정보.

## **> 쿠키 처리하기**

>> code
var cookieParser = require('cookie-parser');
....
app.use(cookieParser());
....
var router = express.Router();
router.route('/process/showCookie').get(function(req, res){ console.log('/process/showCookie 호출'); res.send(req.cookies);
});
router.route('/process/setUserCookie').get(function(req, res){ console.log('/process/setUserCookie 호출'); res.cookie('user', { id: 'boy', name: '찰리', authorized: true }); res.redirect('/process/showCookie');
});
app.use('/', router);

## >> 설치

npm install cookie-parser --save
**> 세션처리하기**
로그인하면 세션 생성, 로그아웃하면 세션 삭제 -> 로그인하기 전까지 접근을 제한할 수 있음.

## >> 설치

npm install express-session --save

>> code
var cookieParser = require('cookie-parser');
var bodyParser = require('body-parser');
....
app.use(cookieParser());
app.use(expressSession({ secret: 'my key', resave: true, saveUninitialized: true
}));
var router = express.Router();
// session check
router.route('/process/product').get(function(req, res) { console.log('/process/product 호출됨'); if (req.session.user) { res.redirect('/html/product.html'); } else { res.redirect('/html/login2.html'); }
});
app.use('/', router);

// login
router.route('/process/login').pose( function(req, res) { console.log('/process/login 호출'); 

var paramId = req.body.id || req.query.id; 

var paramPassword = req.body.password || req.query.password; if (req.session.user) { 

console.log('이미 로그인되어 상품 페이지로 이동됩니다.'); 

res.redirect('/public/product.html');

 } 

else { **req.session.user** = { id: paramId, name: 'boy', authorized: true }; 

res.writeHead('200', { 'Content-Type': 'text/html;charset=utf8' }); 

res.write('<h1>로그인 성공</h1>'); 

res.write('<div><p>Param id: ' + paramId + '</p></div>'); 

res.write('<div><p>Param password: ' + paramPassword + '</p></div>'); 

res.write("<br><br> <a href='/process/product'>상품 페이지로 이동하기</a>"); res.end(); }
});

router.route('/process/logout').get(function(req, res) { console.log('/process/logout 호출됨');

 if (req.session.user) { console.log('로그아웃합니다.'); 

**req.session.destroy**(function(err){ if (err) { throw err;} console.log('세션을 삭제하고 로그아웃되었습니다');

 res.redirect('/public/login2.html'); }); } else { console.log('아직 로그인되어 있지 않습니다.'); 

res.redirect('/public/login2.html'); }
});