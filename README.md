<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Luna Mok 的个人名片</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #74ebd5, #ACB6E5);
      text-align: center;
      padding: 50px;
      color: #333;
    }
    .card {
      background: #fff;
      border-radius: 15px;
      box-shadow: 0px 4px 12px rgba(0,0,0,0.1);
      padding: 30px;
      display: inline-block;
      max-width: 400px;
    }
    h1 {
      margin: 0;
      font-size: 24px;
    }
    p {
      color: #555;
    }
    .btn {
      display: inline-block;
      margin: 10px;
      padding: 10px 20px;
      border-radius: 25px;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }
    .twitter {
      background: #1DA1F2;
      color: #fff;
    }
    .twitter:hover {
      background: #0d8ddb;
    }
    .wechat {
      background: #09b83e;
      color: #fff;
    }
    .wechat:hover {
      background: #069a31;
    }
    audio {
      margin-top: 15px;
      width: 100%;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Luna Mok</h1>
    <p>欢迎来到我的个人主页 🌸</p>
    <a href="https://twitter.com/" target="_blank" class="btn twitter">关注我的 Twitter</a>
    <a href="weixin://" class="btn wechat">加我微信</a>
    
    <!-- 音频播放器 -->
    <audio controls>
      <source src="music.mp3" type="audio/mpeg">
      你的浏览器不支持播放音频
    </audio>
  </div>
</body>
</html>
