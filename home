<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Transforme sua Vida com Autocuidado</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Open+Sans&display=swap" rel="stylesheet">
<style>
body{font-family:'Open Sans',sans-serif;margin:0;padding:0;background:#fdfdfd;color:#333;}
header{background:linear-gradient(120deg,#dff6f0,#c2f0e0);padding:60px 20px;text-align:center;position:relative;}
h1{font-family:'Montserrat',sans-serif;font-size:2.8em;color:#0b6e4f;margin-bottom:10px;}
p.subtitle{font-size:1.3em;margin-bottom:30px;color:#1f4e79;}
button{background:#ff5722;color:white;border:none;padding:16px 40px;border-radius:12px;font-size:1.3em;cursor:pointer;transition:0.3s;}
button:hover{background:#e64a19;transform:translateY(-3px);}
#ebookCover{width:250px;border-radius:12px;box-shadow:0 8px 25px rgba(0,0,0,0.2);margin:20px auto;display:block;}
#ebookPrice{margin:20px 0;font-weight:bold;font-size:1.5em;}
#ebookPrice span.old{text-decoration:line-through;color:#888;margin-right:10px;font-size:1.2em;}
#offer {color:#ff0000;font-weight:bold;font-size:1.2em;animation:blink 1s infinite;}
#buyers{margin:15px 0;font-size:1.2em;color:#1f4e79;}
.comment-box{position:fixed;right:20px;bottom:50px;width:250px;background:#e0f7fa;padding:15px;border-radius:12px;box-shadow:0 4px 15px rgba(0,0,0,0.2);font-size:0.9em;display:none;opacity:0;transition:0.5s;}
.comment-box p{margin:0;text-align:left;font-style:italic;}
.container{max-width:700px;margin:40px auto;padding:20px;text-align:center;}
.progress-bar {width:100%;background:#e0e0e0;border-radius:10px;margin:20px 0;height:20px;}
.progress {height:100%;width:0%;background:#0b6e4f;border-radius:10px;transition:0.5s;}
#result {display:none;margin-top:30px;}
#ebookPreview{text-align:left;background:#f1f9f8;padding:20px;border-radius:12px;margin:20px 0;max-height:200px;overflow:auto;}
@keyframes blink{0%{opacity:1;}50%{opacity:0;}100%{opacity:1;}}
@media(max-width:768px){h1{font-size:2em;}button{width:90%;} #ebookCover{width:180px;} .comment-box{width:200px;}}
</style>
</head>
<body>

<header>
<h1>Transforme seu Autocuidado Hoje!</h1>
<p class="subtitle">Descubra seus hábitos e melhore sua vida com nosso e-book completo</p>
<img id="ebookCover" src="capa_ebook.jpg" alt="Capa do E-book">
<p id="ebookPrice">
  <span class="old">R$49,90</span>
  <span>R$19,90</span>
  <span id="offer">Oferta válida até hoje!</span>
</p>
<p id="buyers">Mais de <span id="buyerCount">1.254</span> pessoas já adquiriram este e-book!</p>
<button onclick="startQuiz()">Começar Teste Gratuitamente</button>
</header>

<div class="container" id="quiz" style="display:none;">
  <h2>Teste seu Autocuidado!</h2>
  <p id="question"></p>
  <div id="answers"></div>
  <div class="progress-bar"><div class="progress" id="progress"></div></div>
</div>

<div id="result">
  <h2>Parabéns!</h2>
  <p id="score"></p>
  <img src="capa_ebook.jpg" alt="Capa do E-book" style="width:200px;border-radius:10px;margin:10px 0;">
  <div id="ebookPreview">
    <h3>Prévia do E-book:</h3>
    <p>Descubra hábitos simples que podem transformar seu dia a dia. Aprenda técnicas de autocuidado, mindfulness, planejamento de metas e muito mais. Este é apenas um trecho do conteúdo completo que vai mudar sua vida.</p>
  </div>
  <p><strong>Preço promocional: <span style="text-decoration:line-through">R$49,90</span> → R$19,90</strong></p>
  <button onclick="buyEbook()">Quero meu E-book!</button>
</div>

<div id="commentBox" class="comment-box"><p></p></div>

<script>
// Comentários pop-up
const comments = [
"Adorei o e-book! Mudou meus hábitos diários 😍",
"Super útil! Comecei a praticar autocuidado e estou mais feliz 🙂",
"Vale cada centavo! Recomendo para todos!",
"Incrível, dicas práticas e fáceis de aplicar!",
"Comprei ontem e já notei resultados positivos!"
];
function startComments(){
  const commentBox = document.getElementById('commentBox');
  let i=0;
  setInterval(()=>{
    commentBox.querySelector('p').innerText = comments[i % comments.length];
    commentBox.style.display='block';
    commentBox.style.opacity='1';
    setTimeout(()=>{commentBox.style.opacity='0';},4000);
    i++;
  },5000);
}
startComments();

// Contador compradores
let buyerCount = 1254;
function startBuyerCounter(){
  const buyerSpan = document.getElementById('buyerCount');
  let displayed = 0;
  const interval = setInterval(()=>{
    if(displayed<buyerCount){
      displayed+=Math.floor(Math.random()*5)+1;
      if(displayed>buyerCount) displayed=buyerCount;
      buyerSpan.innerText=displayed;
    } else clearInterval(interval);
  },100);
}
startBuyerCounter();

// Quiz 8 perguntas
const quizData = [
{q:"Você costuma reservar momentos para você mesmo?", a:["Sempre","Às vezes","Quase nunca"], correct:0},
{q:"Você dorme pelo menos 7 horas por noite?", a:["Sim","Às vezes","Não"], correct:0},
{q:"Você se hidrata adequadamente ao longo do dia?", a:["Sim","Às vezes","Não"], correct:0},
{q:"Você pratica exercícios regularmente?", a:["Sim, sempre","Às vezes","Nunca"], correct:0},
{q:"Você consegue dizer não quando necessário?", a:["Sim","Às vezes","Não"], correct:0},
{q:"Você sente que controla o estresse do dia a dia?", a:["Sim","Mais ou menos","Não"], correct:0},
{q:"Você faz pausas durante o trabalho ou estudos?", a:["Sim, regularmente","Às vezes","Não"], correct:0},
{q:"Você mantém uma alimentação equilibrada?", a:["Sim","Às vezes","Não"], correct:0}
];

let current=0,score=0;

function startQuiz(){
  document.getElementById('quiz').style.display="block";
  window.scrollTo(0, document.getElementById('quiz').offsetTop);
  loadQuestion();
}

function loadQuestion(){
  const q = quizData[current];
  document.getElementById("question").innerText = q.q;
  const answersDiv = document.getElementById("answers");
  answersDiv.innerHTML = "";
  q.a.forEach((ans,i)=>{
    const btn=document.createElement("button");
    btn.innerText=ans;
    btn.onclick=()=>selectAnswer(i);
    answersDiv.appendChild(btn);
  });
  document.getElementById("progress").style.width=((current/quizData.length)*100)+"%";
}

function selectAnswer(i){
  if(i===quizData[current].correct) score++;
  current++;
  if(current<quizData.length) loadQuestion();
  else showResult();
}

function showResult(){
  document.getElementById("quiz").style.display="none";
  document.getElementById("result").style.display="block";
  document.getElementById("score").innerText="Você acertou "+score+" de "+quizData.length+" perguntas!";
}

// Botão para Kiwify
function buyEbook(){
  window.location.href="https://pay.kiwify.com.br/AqJxIr4"; // substitua pelo seu link real
}
</script>

</body>
</html>
