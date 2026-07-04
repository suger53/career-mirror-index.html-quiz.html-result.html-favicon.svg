
career-mirror/
 ├ index.html
 ├ quiz.html
 ├ result.html
 ├ favicon.svg
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Career Mirror</title>
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

.glow{
    position:absolute;
    width:600px;
    height:600px;
    background: radial-gradient(circle, rgba(37,99,235,0.25), transparent 60%);
    filter: blur(60px);
    top:-150px;
    left:-150px;
}

.container{
    max-width:700px;
    padding:20px;
}

.logo{
    font-size:14px;
    letter-spacing:3px;
    color:#93C5FD;
    margin-bottom:25px;
}

h1{
    font-size:44px;
    margin-bottom:10px;
}

p{
    color:#9CA3AF;
    line-height:1.8;
    margin-bottom:35px;
}

.btn{
    display:inline-block;
    padding:16px 42px;
    border-radius:12px;
    background: linear-gradient(90deg,#2563EB,#22C55E);
    color:white;
    font-weight:600;
    text-decoration:none;
    transition:0.3s;
}

.btn:hover{
    transform:translateY(-3px);
}
</style>
</head>

<body>

<div class="glow"></div>

<div class="container">

<div class="logo">🪞 CAREER MIRROR</div>

<h1>未来のあなたを、映し出す。</h1>

<p>
たった3分で「社会人としての信頼度」がわかる<br>
自己分析ツール
</p>

<a href="quiz.html" class="btn">診断をはじめる</a>

</div>

</body>
</html>
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>診断 - Career Mirror</title>
<link rel="icon" href="favicon.svg">

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

.card{
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    padding:20px;
    border-radius:16px;
    margin-bottom:15px;
}

.q{
    margin-bottom:10px;
}

label{
    display:block;
    margin:6px 0;
    color:#CBD5E1;
}

.btn{
    width:100%;
    padding:16px;
    border:none;
    border-radius:12px;
    background: linear-gradient(90deg,#2563EB,#22C55E);
    color:white;
    font-weight:600;
    margin-top:20px;
}
</style>
</head>

<body>

<div class="container">

<a href="index.html" style="color:#93C5FD;">← 戻る</a>

<form id="quizForm">

<!-- Q1〜Q20 -->
<script>
const questions = [
"成果を最優先に考える",
"個人で結果を出す方が得意",
"周囲の意見をよく聞く",
"責任ある役割が好き",
"人の気持ちを考えて行動する",
"効率を重視して動く",
"競争はモチベーションになる",
"チームワークを大事にする",
"自分の意見をはっきり言う",
"空気を読むのが得意",
"リーダー役を任されたい",
"慎重に判断するタイプだ",
"目標達成への意欲が強い",
"他人のサポートが得意",
"成果が評価されると嬉しい",
"トラブル時に前に出る",
"周囲との調和を意識する",
"改善点を見つけるのが得意",
"ストレス耐性は高い",
"自分の成長を最優先に考える"
];

for(let i=0;i<questions.length;i++){
document.write(`
<div class="card">
<div class="q">Q${i+1}. ${questions[i]}</div>

<label><input type="radio" name="q${i+1}" value="5">そう思う</label>
<label><input type="radio" name="q${i+1}" value="3">どちらでも</label>
<label><input type="radio" name="q${i+1}" value="1">思わない</label>

</div>
`);
}
</script>

<button class="btn" type="submit">結果を見る</button>

</form>

</div>

<script>
document.getElementById("quizForm").addEventListener("submit", function(e){
    e.preventDefault();

    let score = 0;

    for(let i=1;i<=20;i++){
        let v = document.querySelector(`input[name=q${i}]:checked`);
        if(!v){
            alert("未回答があります");
            return;
        }
        score += Number(v.value);
    }

    // 20問×5点 = 最大100点 → そのまま％にできる
    let bj = score;

    localStorage.setItem("score", bj);
    location.href = "result.html";
});
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>結果 - Career Mirror</title>
<link rel="icon" href="favicon.svg">

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

/* カード */
.card{
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    padding:22px;
    border-radius:16px;
    margin-bottom:15px;
}

/* パーセント表示 */
.big{
    font-size:64px;
    font-weight:800;
    color:#60A5FA;
}

/* タイプ */
.type{
    font-size:20px;
    font-weight:600;
    margin-top:10px;
}

/* 説明 */
.desc{
    color:#9CA3AF;
    line-height:1.8;
    margin-top:10px;
}

/* バー */
.bar{
    height:10px;
    background:#111827;
    border-radius:10px;
    overflow:hidden;
    margin-top:15px;
}

.fill{
    height:100%;
    width:0%;
    background: linear-gradient(90deg,#2563EB,#22C55E);
    transition:1s ease;
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
    margin-top:10px;
    cursor:pointer;
}

/* シェア */
.share{
    margin-top:10px;
    font-size:13px;
    color:#9CA3AF;
}
</style>
</head>

<body>

<div class="container">

<div class="card">
<h2>あなたの診断結果</h2>

<div class="big" id="score">--%</div>

<div class="bar">
<div class="fill" id="bar"></div>
</div>

<div class="type" id="type">---</div>

<div class="desc" id="desc"></div>
</div>

<button class="btn" onclick="share()">結果をシェアする</button>

<button class="btn" onclick="location.href='quiz.html'">もう一度診断</button>

<div class="share">※Career Mirrorは自己分析ツールです</div>

</div>

<script>
let score = Number(localStorage.getItem("score")) || 0;

// タイプ判定
let type = "";
let desc = "";

if(score >= 85){
    type = "ブリリアント・リーダー型";
    desc = "圧倒的な成果志向とリーダー性を持つタイプ。周囲を巻き込みながら結果を出す力があるが、独走しすぎには注意。";
}
else if(score >= 70){
    type = "ストラテジック型";
    desc = "論理性とバランスを持つ優秀タイプ。冷静な判断力で組織に貢献できる。";
}
else if(score >= 50){
    type = "バランス型";
    desc = "協調性と個人力のバランスが取れた安定型。環境適応力が高い。";
}
else if(score >= 30){
    type = "サポート型";
    desc = "周囲を支える力が強いタイプ。縁の下の力持ちとして評価されやすい。";
}
else{
    type = "ピュア協調型";
    desc = "人間関係を重視する優しさ特化型。チームの安心感を作る存在。";
}

document.getElementById("score").innerText = score + "%";
document.getElementById("type").innerText = type;
document.getElementById("desc").innerText = desc;

// バーアニメーション
setTimeout(()=>{
    document.getElementById("bar").style.width = score + "%";
},200);

// シェア
function share(){
    const text = `私のCareer Mirror結果は「${type}（${score}%）」でした！`;
    navigator.clipboard.writeText(text);
    alert("コピーしました！");
}
</script>

</body>
</html>