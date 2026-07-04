<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Career Mirror</title>

<!-- ファビコン -->
<link rel="icon" href="favicon.svg" type="image/svg+xml">

<style>
body{
    margin:0;
    font-family:"Segoe UI","Noto Sans JP",sans-serif;
    background: radial-gradient(circle at top, #0B1220, #05070F);
    color:#E5E7EB;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    text-align:center;
    overflow:hidden;
}

/* 光エフェクト */
.glow{
    position:absolute;
    width:600px;
    height:600px;
    background: radial-gradient(circle, rgba(37,99,235,0.25), transparent 60%);
    filter: blur(60px);
    top:-150px;
    left:-150px;
}

/* コンテンツ */
.container{
    max-width:700px;
    padding:20px;
    z-index:2;
}

/* ロゴ */
.logo{
    display:flex;
    justify-content:center;
    align-items:center;
    gap:10px;
    margin-bottom:25px;
}

/* タイトル */
h1{
    font-size:44px;
    margin-bottom:10px;
    font-weight:700;
}

/* 説明 */
p{
    color:#9CA3AF;
    line-height:1.8;
    margin-bottom:35px;
}

/* ボタン */
.btn{
    display:inline-block;
    padding:16px 42px;
    border-radius:12px;
    background: linear-gradient(90deg,#2563EB,#22C55E);
    color:white;
    font-weight:600;
    text-decoration:none;
    transition:0.3s;
    box-shadow:0 10px 40px rgba(37,99,235,0.25);
}

.btn:hover{
    transform:translateY(-3px);
    box-shadow:0 15px 60px rgba(37,99,235,0.35);
}

/* 小テキスト */
.small{
    margin-top:20px;
    font-size:12px;
    color:#6B7280;
}
</style>

</head>

<body>

<div class="glow"></div>

<div class="container">

<!-- ロゴ -->
<div class="logo">
<svg width="28" height="28" viewBox="0 0 24 24" fill="none">
  <path d="M12 2C8 2 5 5 5 9c0 3 2 5 5 7l2 1 2-1c3-2 5-4 5-7 0-4-3-7-7-7z"
        stroke="#60A5FA" stroke-width="1.5"/>
  <path d="M8 10h8" stroke="#34D399" stroke-width="1.5"/>
</svg>

<div style="font-size:14px;letter-spacing:3px;color:#93C5FD;">
CAREER MIRROR
</div>
</div>

<!-- メイン -->
<h1>未来のあなたを、映し出す。</h1>

<p>
たった3分で、あなたの<br>
「社会人としての信頼される力」が見える。<br><br>
就活生のための自己分析ツール。
</p>

<!-- ボタン -->
<a href="quiz.html" class="btn">診断をはじめる</a>

<!-- 補足 -->
<div class="small">
無料 / 登録不要 / 3分で完了
</div>

</div>

</body>
</html>
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Career Mirror - 診断</title>

<link rel="icon" href="favicon.svg" type="image/svg+xml">

<style>
body{
    margin:0;
    font-family:"Segoe UI","Noto Sans JP",sans-serif;
    background: radial-gradient(circle at top, #0B1220, #05070F);
    color:#E5E7EB;
    padding:30px 20px;
}

.container{
    max-width:700px;
    margin:0 auto;
}

/* ヘッダー */
.header{
    margin-bottom:25px;
}

.logo{
    font-size:12px;
    letter-spacing:3px;
    color:#93C5FD;
}

/* カード */
.card{
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    padding:20px;
    border-radius:16px;
    margin-bottom:15px;
}

/* 質問 */
.q{
    font-size:16px;
    margin-bottom:12px;
}

/* 選択肢 */
label{
    display:block;
    margin:8px 0;
    color:#CBD5E1;
    cursor:pointer;
}

input{
    margin-right:8px;
}

/* ボタン */
.btn{
    width:100%;
    padding:16px;
    border:none;
    border-radius:12px;
    background: linear-gradient(90deg,#2563EB,#22C55E);
    color:white;
    font-weight:600;
    cursor:pointer;
    margin-top:20px;
    transition:0.3s;
}

.btn:hover{
    transform:translateY(-2px);
}

/* 戻る */
.back{
    display:inline-block;
    margin-bottom:20px;
    color:#93C5FD;
    text-decoration:none;
    font-size:13px;
}
</style>

</head>

<body>

<div class="container">

<!-- 戻る -->
<a class="back" href="index.html">← トップに戻る</a>

<!-- ロゴ -->
<div class="header">
<div class="logo">CAREER MIRROR / DIAGNOSIS</div>
</div>

<form id="quizForm">

<!-- Q1 -->
<div class="card">
<div class="q">Q1. 仕事では成果を最優先に考える</div>
<label><input type="radio" name="q1" value="5"> そう思う</label>
<label><input type="radio" name="q1" value="3"> どちらでもない</label>
<label><input type="radio" name="q1" value="1"> そう思わない</label>
</div>

<!-- Q2 -->
<div class="card">
<div class="q">Q2. チームよりも個人で結果を出す方が得意だ</div>
<label><input type="radio" name="q2" value="5"> そう思う</label>
<label><input type="radio" name="q2" value="3"> どちらでもない</label>
<label><input type="radio" name="q2" value="1"> そう思わない</label>
</div>

<!-- Q3 -->
<div class="card">
<div class="q">Q3. 周囲の意見をよく聞いて判断する</div>
<label><input type="radio" name="q3" value="5"> そう思う</label>
<label><input type="radio" name="q3" value="3"> どちらでもない</label>
<label><input type="radio" name="q3" value="1"> そう思わない</label>
</div>

<!-- Q4 -->
<div class="card">
<div class="q">Q4. 責任のある役割を任されると燃える</div>
<label><input type="radio" name="q4
