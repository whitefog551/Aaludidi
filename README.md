<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Rakhi — Aalu Didi</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg1: #fffafc;
    --bg2: #ffeef2;
    --accent: #ff4d88;
    --text: #222;
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    min-height:100vh;
    background: linear-gradient(180deg, var(--bg1), var(--bg2));
    font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, Arial;
    color:var(--text);
    display:flex;
    align-items:center;
    justify-content:center;
    padding:18px;
    overflow:hidden;
  }
  .stage{
    width:100%;
    max-width:720px;
    text-align:center;
  }
  .title{
    font-weight:600;
    color:var(--accent);
    font-size: clamp(28px, 8vw, 48px);
    margin:0 0 20px;
    opacity:0;
    animation: fadeIn 1s ease forwards;
  }
  @keyframes fadeIn {
    from{opacity:0; transform:translateY(10px)}
    to{opacity:1; transform:translateY(0)}
  }
  .paper {
    width: 100%;
    background: rgba(255,255,255,0.9);
    border-radius: 14px;
    padding: 16px 18px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.08);
    text-align:left;
    font-size: clamp(15px, 3vw, 19px);
    line-height:1.45;
    white-space: pre-wrap;
    opacity:0;
    transform: translateY(18px);
    animation: fadeUp 0.8s ease forwards;
    animation-delay: 0.4s;
  }
  @keyframes fadeUp {
    to{opacity:1; transform:translateY(0)}
  }
  .cursor {
    display:inline-block;
    width:6px;
    height:18px;
    background:var(--accent);
    margin-left:4px;
    animation: blink 900ms steps(1) infinite;
  }
  @keyframes blink{50%{opacity:0}}
</style>
</head>
<body>
  <div class="stage">
    <h1 class="title">Aalu Didi</h1>
    <div id="paper" class="paper">
      <div id="typedText"></div><span id="cursor" class="cursor"></span>
    </div>
  </div>

<script>
const messageLines = [
  "Your brother never wanted you to be alone or sad,",
  "Even if he is far away from you,",
  "His wishes and love are always with you,",
  "Stay strong — you're never alone,",
  "Best wishes to you for this rakhi,",
  "",
  "From me... Thank you Aalu didi,",
  "For coming into my life,",
  "And being one of the best parts of my life,",
  "I'll tell you more about this but not now,",
  "Kabhi nii jaana chordke......",
  "Ye toh nii bolsaktaa soo yahhh,",
  "Thank youu Aalu didi 🥰,",
  "",
  "Happy Rakshabandhan 🌸"
];

const typedText = document.getElementById('typedText');
const cursor = document.getElementById('cursor');

function typeLines(lines, speed=90){
  let lineIndex = 0;
  function typeLine(){
    if(lineIndex >= lines.length){
      cursor.style.display = 'none';
      return;
    }
    let line = lines[lineIndex];
    let charIndex = 0;
    function typeChar(){
      if(charIndex < line.length){
        typedText.textContent += line.charAt(charIndex);
        charIndex++;
        setTimeout(typeChar, speed);
      } else {
        typedText.textContent += "\n";
        lineIndex++;
        setTimeout(typeLine, 300);
      }
    }
    typeChar();
  }
  typeLine();
}

typeLines(messageLines, 85);
</script>
</body>
</html>
