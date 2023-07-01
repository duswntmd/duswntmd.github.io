---
layout: post
title:  "mysql과 node.js를 이용한 DB연결"
---
하나의 DB연결 예시이다.
```
const pool = mysql.createPool({
  connectionLimit: 10,
  host: dbconfig.host,
  user: dbconfig.user,
  password: dbconfig.password,
  port: dbconfig.port,
  database: dbconfig.database,
  debug: false,
});
```
mysql 안의 table 정보를 얻기 위해서는 mysql 로그인 정보를 적어야 한다.
```
// 회원가입 처리 라우팅
app.post("/process/adduser", (req, res) => {
  console.log("/process/adduser 호출됨" + req);
  const paramId = req.body.id;
  const paramName = req.body.name;
  const paramAge = req.body.age;
  const paramPassword = req.body.password;
  // 데이터베이스 연결 풀에서 커넥션을 가져옵니다.
  pool.getConnection((err, conn) => {
    if (err) {
      conn.release();
      console.log("Mysql getConnection error. aborted");
      res.writeHead("200", { "content-type": "text/html; charset=utf8" });
      res.write("<h1>DB서버 연결 실패</h1>");
      res.end();
      return;
    }
    console.log("데이터베이스 연결 끈 얻었음...ㅎㅎ");
    // 사용자 생성을 위해 데이터베이스에서 쿼리를 실행합니다.
    const exec = conn.query(
      "insert into users (id, name, age, password) values (?,?,?,md5(?));",
      [paramId, paramName, paramAge, paramPassword],
      (err, result) => {
        conn.release();
        console.log("실행된 SQL: " + exec.sql);
        if (err) {
          console.log("SQL 실행시 오류 발생");
          console.dir(err);
          res.writeHead("200", { "content-type": "text/html; charset=utf8" });
          res.write("<h1>SQL query 실행 실패</h1>");
          res.end();
          return;
        }
        if (result) {
          console.dir(result);
          console.log("Inserted 성공");

          res.writeHead("200", { "content-type": "text/html; charset=utf8" });
          res.write("<h2>사용자 추가 성공</h2>");
          res.end();
        } else {
          console.log("Inserted 실패");

          res.writeHead("200", { "content-type": "text/html; charset=utf8" });
          res.write("<h1>사용자 추가 실패</h1>");
          res.end();
        }
      }
    );
  });
});
```
html에서의 정보를 post형식으로 가져온다. 
그리고 DB의 정보를 확인한다.
DB의 정보가 맞다면 insert한다 위 예시는 users라는 table에 저장하겠다는 뜻이다.
DB의 table장소가 있다면 잘 들어가는 것을 볼 수 있다.
