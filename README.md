<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Spesial Buat Nadhira 💌</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Quicksand:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --pink: #ff6b9d;
    --soft-pink: #ffd6e7;
    --rose: #c9184a;
    --cream: #fff0f5;
    --dark: #2d1b2e;
    --gold: #f4a261;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Quicksand', sans-serif;
    background: var(--cream);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow-x: hidden;
    position: relative;
  }

  /* Floating hearts background */
  .hearts-bg {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    overflow: hidden;
    z-index: 0;
  }

  .heart-float {
    position: absolute;
    bottom: -50px;
    font-size: 20px;
    animation: floatUp linear infinite;
    opacity: 0.15;
  }

  @keyframes floatUp {
    0% { transform: translateY(0) rotate(0deg); opacity: 0.15; }
    100% { transform: translateY(-110vh) rotate(360deg); opacity: 0; }
  }

  .container {
    position: relative;
    z-index: 1;
    width: 100%;
    max-width: 520px;
    margin: 20px auto;
    padding: 20px;
  }

  /* INTRO SCREEN */
  #intro-screen {
    text-align: center;
    animation: fadeIn 1s ease;
  }

  .envelope-wrap {
    margin: 0 auto 30px;
    width: 120px;
    height: 90px;
    position: relative;
    cursor: pointer;
    animation: bounce 2s ease-in-out infinite;
  }

  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-12px); }
  }

  .envelope {
    width: 120px;
    height: 90px;
    background: linear-gradient(135deg, #ff6b9d, #c9184a);
    border-radius: 8px;
    position: relative;
    box-shadow: 0 8px 25px rgba(201,24,74,0.3);
  }

  .envelope::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    border-top: 45px solid #e05585;
    border-left: 60px solid transparent;
    border-right: 60px solid transparent;
  }

  .envelope::after {
    content: '💌';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -20%);
    font-size: 30px;
  }

  .intro-title {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    color: var(--rose);
    margin-bottom: 10px;
    line-height: 1.2;
  }

  .intro-title span {
    color: var(--pink);
    font-style: italic;
  }

  .intro-subtitle {
    color: #888;
    font-size: 0.95rem;
    margin-bottom: 30px;
    line-height: 1.6;
  }

  .btn-start {
    background: linear-gradient(135deg, var(--pink), var(--rose));
    color: white;
    border: none;
    padding: 16px 45px;
    border-radius: 50px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1.1rem;
    font-weight: 600;
    cursor: pointer;
    box-shadow: 0 6px 20px rgba(255,107,157,0.4);
    transition: all 0.3s ease;
    letter-spacing: 0.5px;
  }

  .btn-start:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 30px rgba(255,107,157,0.5);
  }

  /* QUIZ CARD */
  .quiz-card {
    background: white;
    border-radius: 24px;
    padding: 35px 30px;
    box-shadow: 0 15px 50px rgba(201,24,74,0.12);
    animation: slideUp 0.5s ease;
    border: 1px solid rgba(255,107,157,0.15);
  }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .progress-bar-wrap {
    background: var(--soft-pink);
    border-radius: 10px;
    height: 8px;
    margin-bottom: 25px;
    overflow: hidden;
  }

  .progress-bar {
    height: 100%;
    background: linear-gradient(90deg, var(--pink), var(--rose));
    border-radius: 10px;
    transition: width 0.5s ease;
  }

  .question-num {
    font-size: 0.8rem;
    color: var(--pink);
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .question-text {
    font-family: 'Playfair Display', serif;
    font-size: 1.35rem;
    color: var(--dark);
    margin-bottom: 25px;
    line-height: 1.5;
  }

  .options-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }

  .option-btn {
    background: var(--cream);
    border: 2px solid transparent;
    border-radius: 14px;
    padding: 14px 18px;
    text-align: left;
    cursor: pointer;
    font-family: 'Quicksand', sans-serif;
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--dark);
    transition: all 0.25s ease;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .option-btn:hover {
    border-color: var(--pink);
    background: var(--soft-pink);
    transform: translateX(5px);
  }

  .option-btn.selected {
    border-color: var(--rose);
    background: linear-gradient(135deg, #fff0f5, #ffd6e7);
    color: var(--rose);
    font-weight: 600;
  }

  .option-letter {
    width: 30px; height: 30px;
    border-radius: 50%;
    background: white;
    display: flex; align-items: center; justify-content: center;
    font-weight: 700;
    font-size: 0.85rem;
    color: var(--pink);
    flex-shrink: 0;
    border: 2px solid var(--soft-pink);
  }

  .selected .option-letter {
    background: var(--rose);
    color: white;
    border-color: var(--rose);
  }

  .btn-next {
    margin-top: 25px;
    width: 100%;
    background: linear-gradient(135deg, var(--pink), var(--rose));
    color: white;
    border: none;
    padding: 15px;
    border-radius: 14px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    display: none;
  }

  .btn-next:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255,107,157,0.4);
  }

  /* REACTION POPUP */
  .reaction-popup {
    position: fixed;
    bottom: 30px; left: 50%;
    transform: translateX(-50%) translateY(100px);
    background: white;
    border-radius: 20px;
    padding: 16px 24px;
    box-shadow: 0 10px 40px rgba(0,0,0,0.12);
    font-size: 1rem;
    font-weight: 600;
    color: var(--rose);
    z-index: 100;
    text-align: center;
    border: 2px solid var(--soft-pink);
    transition: transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
    max-width: 300px;
    width: 90%;
  }

  .reaction-popup.show {
    transform: translateX(-50%) translateY(0);
  }

  /* RESULT SCREEN */
  #result-screen {
    text-align: center;
    animation: fadeIn 1s ease;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .result-card {
    background: white;
    border-radius: 24px;
    padding: 40px 30px;
    box-shadow: 0 15px 50px rgba(201,24,74,0.15);
    border: 1px solid rgba(255,107,157,0.2);
  }

  .result-emoji {
    font-size: 4rem;
    margin-bottom: 15px;
    display: block;
    animation: heartbeat 1s ease-in-out infinite;
  }

  @keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.15); }
  }

  .result-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    color: var(--rose);
    margin-bottom: 10px;
    line-height: 1.3;
  }

  .result-subtitle {
    color: #888;
    font-size: 0.95rem;
    margin-bottom: 20px;
  }

  .love-message {
    background: linear-gradient(135deg, var(--cream), var(--soft-pink));
    border-radius: 16px;
    padding: 20px;
    margin: 20px 0;
    border-left: 4px solid var(--pink);
    text-align: left;
  }

  .love-message p {
    color: var(--dark);
    line-height: 1.7;
    font-size: 0.95rem;
  }

  .love-message .from {
    margin-top: 12px;
    font-weight: 700;
    color: var(--rose);
    font-style: italic;
  }

  .recap-box {
    background: var(--cream);
    border-radius: 16px;
    padding: 18px;
    margin: 20px 0 14px;
    text-align: left;
    border: 1px solid var(--soft-pink);
  }

  .recap-box h4 {
    color: var(--rose);
    font-size: 0.85rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 12px;
    font-weight: 700;
  }

  .recap-item {
    margin-bottom: 10px;
    font-size: 0.88rem;
    color: var(--dark);
    line-height: 1.5;
  }

  .recap-item .rq {
    font-weight: 600;
    color: var(--rose);
    font-size: 0.8rem;
  }

  .recap-item .ra {
    color: #555;
  }

  .btn-wa {
    width: 100%;
    background: linear-gradient(135deg, #25d366, #128c7e);
    color: white;
    border: none;
    padding: 15px;
    border-radius: 14px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-bottom: 12px;
  }

  .btn-wa:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(37,211,102,0.4);
  }
    border: 2px solid var(--pink);
    color: var(--pink);
    padding: 12px 35px;
    border-radius: 50px;
    font-family: 'Quicksand', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 10px;
  }

  .btn-restart:hover {
    background: var(--pink);
    color: white;
  }

  .confetti-piece {
    position: fixed;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    pointer-events: none;
    z-index: 999;
    animation: confettiFall 3s ease forwards;
  }

  @keyframes confettiFall {
    0% { transform: translateY(-10px) rotate(0deg); opacity: 1; }
    100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
  }

  .screen { display: none; }
  .screen.active { display: block; }
</style>
</head>
<body>

<!-- Floating hearts -->
<div class="hearts-bg" id="heartsBg"></div>

<div class="container">

  <!-- INTRO -->
  <div id="intro-screen" class="screen active">
    <div class="envelope-wrap">
      <div class="envelope"></div>
    </div>
    <h1 class="intro-title">Hai, <span>Nadhira</span> 💕</h1>
    <p class="intro-subtitle">Ada seseorang yang iseng<br>buatin quiz spesial buat kamu 😳<br>Berani coba?</p>
    <button class="btn-start" onclick="startQuiz()">Buka Quiz 💌</button>
  </div>

  <!-- QUIZ -->
  <div id="quiz-screen" class="screen">
    <div class="quiz-card">
      <div class="progress-bar-wrap">
        <div class="progress-bar" id="progressBar" style="width:0%"></div>
      </div>
      <div class="question-num" id="questionNum">Pertanyaan 1 dari 8</div>
      <div class="question-text" id="questionText"></div>
      <div class="options-list" id="optionsList"></div>
      <button class="btn-next" id="btnNext" onclick="nextQuestion()">Lanjut →</button>
    </div>
  </div>

  <!-- RESULT -->
  <div id="result-screen" class="screen">
    <div class="result-card">
      <span class="result-emoji">💖</span>
      <h2 class="result-title" id="resultTitle">Kamu Udah Kena Jebakan!</h2>
      <p class="result-subtitle" id="resultSubtitle"></p>
      <div class="love-message">
        <p id="loveMessage"></p>
        <p class="from">— Aria Rasyid 🌹</p>
      </div>
      <div class="recap-box" id="recapBox"></div>
      <button class="btn-wa" id="btnWA" onclick="kirimWA()">💬 Kirim Jawaban ke Aria</button>
      <button class="btn-restart" onclick="restartQuiz()">Main Lagi 🔄</button>
    </div>
  </div>

</div>

<!-- Reaction Popup -->
<div class="reaction-popup" id="reactionPopup"></div>

<script>
  const questions = [
    {
      q: "Kalau Aria tiba-tiba bilang 'Kamu cantik banget hari ini', kamu bakal...",
      opts: [
        "Pura-pura nggak denger terus kabur 😅",
        "Bilang 'Apaan sih' tapi dalam hati seneng banget",
        "Balik kamar terus senyum-senyum sendiri",
        "Langsung salting parah dan lupain nama sendiri"
      ],
      reaction: "Aduh, jujur banget Nadhira! 😂💕"
    },
    {
      q: "Seberapa sering kamu senyum-senyum sendiri gara-gara chat dari Aria? 🤔",
      opts: [
        "Hampir setiap hari jujur aja deh",
        "Kadang-kadang... oke sering sih 😳",
        "Setiap malam sebelum tidur hehe",
        "Ini pertanyaan jebakan ya?"
      ],
      reaction: "Nadhira ketahuaaaan~ 😍"
    },
    {
      q: "Kalau Aria tiba-tiba pegangan tangan, ekspresi wajah kamu bakal...",
      opts: [
        "Merah kayak tomat mateng 🍅",
        "Pura-pura biasa tapi jantung udah disko",
        "Senyum lebar terus nunduk malu",
        "Freeze total, otak nggak bisa mikir"
      ],
      reaction: "Kebayang deh mukanya Nadhira~ 😳💗"
    },
    {
      q: "Jujur, waktu pertama kali ketemu Aria kamu ngerasa...",
      opts: [
        "Biasa aja... (tapi nggak biasa-biasa amat)",
        "Ada sesuatu yang beda dari dia",
        "Deg-degan tapi pura-pura cool",
        "Langsung mikir 'orang ini beda'"
      ],
      reaction: "Nadhira jujur banget hari ini! 🥹"
    },
    {
      q: "Kalau Aria kirim bunga ke rumah kamu, hal pertama yang kamu lakuin adalah...",
      opts: [
        "Foto dulu buat story, caption-nya misterius",
        "Langsung telpon Aria sambil teriak malu-maluin",
        "Simpen di kamar terus senyum-senyum",
        "Nangis terharu terus pura-pura nggak nangis"
      ],
      reaction: "Awww Nadhira imut banget! 🌹😭"
    },
    {
      q: "Kalau Aria bilang 'I love you' secara langsung, kamu bakal...",
      opts: [
        "Langsung beku di tempat 🧊",
        "Balik bilang tapi suaranya nyaris nggak kedengeran",
        "Pura-pura batuk terus kabur ke kamar mandi",
        "Nangis tapi bilang nggak nangis"
      ],
      reaction: "Nadhira pasti lucu banget kalau itu terjadi 😂💞"
    },
    {
      q: "Seberapa sering kamu baca ulang chat Aria yang bikin kamu baper? 😇",
      opts: [
        "Nggak pernah... (bohong)",
        "Jarang... oke lumayan sering",
        "Tiap malam sebelum tidur 🌙",
        "Ini pertanyaan yang terlalu spesifik 😭"
      ],
      reaction: "Nadhira tertangkap basah! 😂💕"
    },
    {
      q: "Terakhir nih~ Menurut kamu, Aria itu...",
      opts: [
        "Annoying tapi bikin kangennn 😤",
        "Nggak romantis tapi perhatian banget",
        "Orang paling spesial yang pernah ada",
        "Semua di atas... makanya disayang 💕"
      ],
      reaction: "Nadhira sayang Aria yaaa~ 🥰🥰🥰"
    }
  ];

  let current = 0;
  let selected = null;
  let answers = [];

  function generateHearts() {
    const bg = document.getElementById('heartsBg');
    const emojis = ['❤️', '💕', '💗', '🌸', '✨', '💖'];
    for (let i = 0; i < 18; i++) {
      const h = document.createElement('div');
      h.className = 'heart-float';
      h.textContent = emojis[Math.floor(Math.random() * emojis.length)];
      h.style.left = Math.random() * 100 + '%';
      h.style.animationDuration = (8 + Math.random() * 12) + 's';
      h.style.animationDelay = (Math.random() * 10) + 's';
      h.style.fontSize = (14 + Math.random() * 16) + 'px';
      bg.appendChild(h);
    }
  }

  function startQuiz() {
    document.getElementById('intro-screen').classList.remove('active');
    document.getElementById('quiz-screen').classList.add('active');
    loadQuestion();
  }

  function loadQuestion() {
    selected = null;
    const q = questions[current];
    document.getElementById('questionNum').textContent = `Pertanyaan ${current + 1} dari ${questions.length}`;
    document.getElementById('questionText').textContent = q.q;
    document.getElementById('progressBar').style.width = ((current / questions.length) * 100) + '%';
    document.getElementById('btnNext').style.display = 'none';

    const list = document.getElementById('optionsList');
    list.innerHTML = '';
    const letters = ['A', 'B', 'C', 'D'];
    q.opts.forEach((opt, i) => {
      const btn = document.createElement('button');
      btn.className = 'option-btn';
      btn.innerHTML = `<span class="option-letter">${letters[i]}</span>${opt}`;
      btn.onclick = () => selectOption(btn, i, q.reaction);
      list.appendChild(btn);
    });
  }

  function selectOption(btn, idx, reaction) {
    document.querySelectorAll('.option-btn').forEach(b => b.classList.remove('selected'));
    btn.classList.add('selected');
    selected = idx;
    document.getElementById('btnNext').style.display = 'block';
    showReaction(reaction);
  }

  function showReaction(text) {
    const popup = document.getElementById('reactionPopup');
    popup.textContent = text;
    popup.classList.add('show');
    setTimeout(() => popup.classList.remove('show'), 2500);
  }

  function nextQuestion() {
    if (selected === null) return;
    answers.push({ q: questions[current].q, a: questions[current].opts[selected] });
    current++;
    if (current < questions.length) {
      loadQuestion();
    } else {
      showResult();
    }
  }

  function showResult() {
    document.getElementById('quiz-screen').classList.remove('active');
    document.getElementById('result-screen').classList.add('active');

    document.getElementById('resultTitle').textContent = "Nadhira, Kamu Resmi Ketahuan! 😍";
    document.getElementById('resultSubtitle').textContent = "Quiz ini bukan quiz biasa... ini surat cinta yang disamarkan 💌";
    document.getElementById('loveMessage').innerHTML = `
      Nadhira Khazbiika Sheevallah,<br><br>
      Quiz ini cuma alasan buat bilang... kamu itu spesial banget buat Aria.
      Setiap senyummu, setiap kali kamu salting, setiap momen bareng kamu —
      semuanya bikin Aria makin sayang sama kamu. 🥹<br><br>
      Semoga kamu tau betapa berharganya kamu, dan semoga hari-hari kita
      penuh dengan momen yang bikin kamu mau senyum-senyum sendiri lagi. 💕<br><br>
      Makasih udah jadi kamu yang apa adanya. Aria sayang Nadhira. 🌹
    `;

    // Render recap
    const recapBox = document.getElementById('recapBox');
    recapBox.innerHTML = '<h4>📋 Rekap Jawaban Nadhira</h4>' + answers.map((a, i) => `
      <div class="recap-item">
        <div class="rq">Q${i+1}: ${a.q}</div>
        <div class="ra">→ ${a.a}</div>
      </div>
    `).join('');

    spawnConfetti();
  }

  function kirimWA() {
    const lines = answers.map((a, i) => `Q${i+1}: ${a.q}\n→ ${a.a}`).join('\n\n');
    const msg = `💌 Hai Aria! Aku udah selesai main quiz-nya~ Ini jawaban aku:\n\n${lines}\n\n— Nadhira 🌸`;
    const url = `https://wa.me/6281912709662?text=${encodeURIComponent(msg)}`;
    window.open(url, '_blank');
  }

  function spawnConfetti() {
    const colors = ['#ff6b9d', '#c9184a', '#ffd6e7', '#f4a261', '#fff0f5', '#ff85b3'];
    for (let i = 0; i < 60; i++) {
      setTimeout(() => {
        const c = document.createElement('div');
        c.className = 'confetti-piece';
        c.style.left = Math.random() * 100 + 'vw';
        c.style.background = colors[Math.floor(Math.random() * colors.length)];
        c.style.width = (6 + Math.random() * 8) + 'px';
        c.style.height = (6 + Math.random() * 8) + 'px';
        c.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
        document.body.appendChild(c);
        setTimeout(() => c.remove(), 3500);
      }, i * 40);
    }
  }

  function restartQuiz() {
    current = 0;
    selected = null;
    answers = [];
    document.getElementById('result-screen').classList.remove('active');
    document.getElementById('intro-screen').classList.add('active');
  }

  generateHearts();
</script>
</body>
</html>
