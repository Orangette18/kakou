<!doctype html>
<html lang="ja">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>加工条件 計算</title>

<style>
body{font-family:system-ui;margin:0}
#loginBox{
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  background:#f5f5f5;
}
.card{
  background:white;
  padding:30px;
  border-radius:12px;
  box-shadow:0 5px 20px rgba(0,0,0,0.1);
  text-align:center;
}
input{padding:8px;border-radius:8px;border:1px solid #ccc}
button{
  padding:8px 14px;
  border:none;
  background:#111;
  color:white;
  border-radius:8px;
  cursor:pointer;
}
#error{color:#b00020;margin-top:10px}
</style>
</head>

<body>

<div id="loginBox">
  <div class="card">
    <h2>社内専用ページ</h2>
    <p>パスワードを入力してください</p>
    <input type="password" id="pw">
    <br><br>
    <button onclick="checkPW()">ログイン</button>
    <div id="error"></div>
  </div>
</div>

<div id="main" style="display:none;">
  <iframe src="app.html" style="width:100%;height:100vh;border:none;"></iframe>
</div>

<script>
// 🔐 パスワード設定
const PASSWORD = "KAKOU37";

function checkPW(){
  const input = document.getElementById("pw").value;
  if(input === PASSWORD){
    document.getElementById("loginBox").style.display="none";
    document.getElementById("main").style.display="block";
  }else{
    document.getElementById("error").innerText="パスワードが違います";
  }
}
</script>

</body>
</html>
