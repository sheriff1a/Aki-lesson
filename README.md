
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>AkiCode Lesson - English Word Learning</title>

  <meta name="description"
        content="AkiCode Lesson helps students learn English words with simple lessons and voice reading.">

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f4f7fb;
      color: #222;
    }

    header {
      background: #1769e0;
      color: white;
      padding: 25px 15px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 30px;
    }

    header p {
      margin: 8px 0 0;
    }

    nav {
      display: flex;
      justify-content: center;
      gap: 8px;
      flex-wrap: wrap;
      padding: 15px;
      background: white;
      box-shadow: 0 2px 8px #ddd;
    }

    nav button {
      border: none;
      background: #1769e0;
      color: white;
      padding: 12px 18px;
      border-radius: 8px;
      font-size: 15px;
      cursor: pointer;
    }

    nav button:hover {
      background: #0d4fac;
    }

    .container {
      max-width: 900px;
      margin: auto;
      padding: 20px;
    }

    .welcome {
      background: white;
      padding: 25px;
      border-radius: 15px;
      margin-bottom: 20px;
      box-shadow: 0 3px 12px #ddd;
      text-align: center;
    }

    .lesson {
      display: none;
    }

    .lesson.active {
      display: block;
    }

    .word-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 12px;
    }

    .word-card {
      background: white;
      padding: 18px 10px;
      border-radius: 12px;
      text-align: center;
      box-shadow: 0 2px 8px #ddd;
    }

    .word {
      font-size: 22px;
      font-weight: bold;
      color: #1769e0;
    }

    .meaning {
      margin: 8px 0;
      font-size: 14px;
    }

    .speak {
      border: none;
      background: #19a974;
      color: white;
      padding: 8px 12px;
      border-radius: 7px;
      cursor: pointer;
    }

    .speak:hover {
      background: #117a52;
    }

    .search {
      width: 100%;
      padding: 14px;
      border: 1px solid #ccc;
      border-radius: 10px;
      margin-bottom: 18px;
      font-size: 16px;
    }

    footer {
      text-align: center;
      padding: 25px;
      margin-top: 30px;
      background: #17202a;
      color: white;
    }

    .big-button {
      background: #1769e0;
      color: white;
      border: none;
      padding: 14px 25px;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 10px;
    }
  </style>
</head>

<body>

<header>
  <h1>📚 AkiCode Lesson</h1>
  <p>Learn English words. Listen. Practice. Improve.</p>
</header>

<nav>
  <button onclick="showLesson('home')">Home</button>
  <button onclick="showLesson('two')">2 Letters</button>
  <button onclick="showLesson('three')">3 Letters</button>
  <button onclick="showLesson('four')">4 Letters</button>
  <button onclick="showLesson('five')">5 Letters</button>
</nav>

<div class="container">

  <section id="home" class="lesson active">
    <div class="welcome">
      <h2>Welcome to AkiCode Lesson 👋</h2>
      <p>
        This website helps you learn English words step by step.
        Choose a word level above and tap 🔊 to hear the pronunciation.
      </p>

      <button class="big-button" onclick="speakText('Welcome to AkiCode Lesson')">
        🔊 Hear Welcome
      </button>
    </div>
  </section>

  <section id="two" class="lesson">
    <h2>2-Letter Words</h2>
    <input class="search" onkeyup="searchWords('two')" 
           placeholder="Search 2-letter words...">

    <div class="word-grid" id="twoWords"></div>
  </section>

  <section id="three" class="lesson">
    <h2>3-Letter Words</h2>
    <input class="search" onkeyup="searchWords('three')" 
           placeholder="Search 3-letter words...">

    <div class="word-grid" id="threeWords"></div>
  </section>

  <section id="four" class="lesson">
    <h2>4-Letter Words</h2>
    <input class="search" onkeyup="searchWords('four')" 
           placeholder="Search 4-letter words...">

    <div class="word-grid" id="fourWords"></div>
  </section>

  <section id="five" class="lesson">
    <h2>5-Letter Words</h2>
    <input class="search" onkeyup="searchWords('five')" 
           placeholder="Search 5-letter words...">

    <div class="word-grid" id="fiveWords"></div>
  </section>

</div>

<footer>
  <p>© 2026 AkiCode Lesson</p>
  <p>Learn • Practice • Speak • Improve</p>
</footer>

<script>

const words = {

  two: [
    ["am","to be"],
    ["an","one or any"],
    ["as","in the same way"],
    ["at","a place or time"],
    ["be","to exist"],
    ["by","near or beside"],
    ["do","to perform"],
    ["go","to move"],
    ["he","a male person"],
    ["if","condition"],
    ["in","inside"],
    ["is","present form of be"],
    ["it","a thing"],
    ["me","a person"],
    ["my","belonging to me"],
    ["no","not any"],
    ["of","belonging to"],
    ["on","above"],
    ["or","choice between things"],
    ["so","therefore"],
    ["up","toward a higher place"],
    ["us","a group including me"],
    ["we","a group including me"]
  ],

  three: [
    ["act","to do something"],
    ["add","put together"],
    ["age","how old someone is"],
    ["air","what we breathe"],
    ["all","everything"],
    ["and","joins words"],
    ["ant","small insect"],
    ["any","one or some"],
    ["arm","part of the body"],
    ["ask","to request information"],
    ["bad","not good"],
    ["bag","container"],
    ["bed","place to sleep"],
    ["big","large"],
    ["box","container"],
    ["boy","young male"],
    ["bus","large vehicle"],
    ["buy","get something by paying"],
    ["car","vehicle"],
    ["cat","animal"],
    ["day","24 hours"],
    ["dog","animal"],
    ["eat","take food"],
    ["eye","part of the body"],
    ["far","a long distance"],
    ["fat","having much body weight"],
    ["few","not many"],
    ["fun","enjoyment"],
    ["get","receive"],
    ["god","deity"],
    ["good","nice or useful"],
    ["hat","head covering"],
    ["hot","high temperature"],
    ["ice","frozen water"],
    ["job","work"],
    ["key","used to open something"],
    ["leg","body part"],
    ["man","adult male"],
    ["map","drawing of a place"],
    ["new","not old"],
    ["old","not new"],
    ["one","number 1"],
    ["red","a colour"],
    ["run","move quickly"],
    ["sad","unhappy"],
    ["see","look at"],
    ["sit","rest on a seat"],
    ["sun","star in the sky"],
    ["top","highest part"],
    ["use","do something with"],
    ["way","method or direction"],
    ["win","be successful"]
  ],

  four: [
    ["able","having the power to do"],
    ["area","a particular place"],
    ["baby","young child"],
    ["back","rear part"],
    ["ball","round object"],
    ["bank","financial institution"],
    ["base","bottom or foundation"],
    ["bath","washing the body"],
    ["beat","hit repeatedly"],
    ["best","most good"],
    ["book","written work"],
    ["born","given life"],
    ["both","two together"],
    ["busy","having work to do"],
    ["call","speak by phone"],
    ["care","look after"],
    ["city","large town"],
    ["class","group of students"],
    ["come","move toward"],
    ["cook","prepare food"],
    ["door","entrance"],
    ["down","toward a lower place"],
    ["draw","make a picture"],
    ["easy","not difficult"],
    ["face","front part of head"],
    ["fact","something true"],
    ["fall","move downward"],
    ["farm","place for growing food"],
    ["fast","quick"],
    ["find","discover"],
    ["fire","heat and light"],
    ["fish","water animal"],
    ["food","something we eat"],
    ["foot","body part"],
    ["game","activity for fun"],
    ["give","hand something to someone"],
    ["girl","young female"],
    ["give","to hand something"],
    ["good","nice"],
    ["hand","body part"],
    ["head","top part of body"],
    ["help","assist"],
    ["home","place where you live"],
    ["hope","want something to happen"],
    ["house","building for living"],
    ["jump","move upward"],
    ["kind","type or caring"],
    ["king","male ruler"],
    ["know","have information"],
    ["land","ground"],
    ["life","state of being alive"],
    ["like","enjoy"],
    ["line","long narrow mark"],
    ["live","have a home"],
    ["long","great in length"],
    ["look","use your eyes"],
    ["love","strong affection"],
    ["make","create"],
    ["many","a large number"],
    ["mind","thinking ability"],
    ["name","word used to identify"],
    ["near","close"],
    ["need","require"],
    ["open","not closed"],
    ["play","take part in a game"],
    ["read","look at written words"],
    ["road","path for vehicles"],
    ["room","space inside a building"],
    ["school","place for education"],
    ["show","let someone see"],
    ["slow","not fast"],
    ["song","music with words"],
    ["star","bright object in sky"],
    ["stay","remain"],
    ["talk","speak"],
    ["time","measure of moments"],
    ["tree","large plant"],
    ["walk","move on feet"],
    ["want","desire"],
    ["work","activity or job"],
    ["year","12 months"]
  ],

  five: [
    ["about","concerning"],
    ["above","higher than"],
    ["after","later than"],
    ["again","one more time"],
    ["apple","fruit"],
    ["beach","sandy place"],
    ["begin","start"],
    ["black","a colour"],
    ["blood","red liquid in body"],
    ["board","flat piece"],
    ["brain","organ used for thinking"],
    ["bread","food made from flour"],
    ["build","construct"],
    ["carry","take something"],
    ["chair","seat"],
    ["child","young person"],
    ["clean","not dirty"],
    ["close","shut"],
    ["cloud","white or grey sky object"],
    ["dance","move to music"],
    ["dream","thought during sleep"],
    ["drink","take liquid"],
    ["early","before expected time"],
    ["earth","planet we live on"],
    ["every","each one"],
    ["family","people related to you"],
    ["father","male parent"],
    ["field","open area"],
    ["floor","bottom surface of room"],
    ["friend","person you like"],
    ["front","forward part"],
    ["green","a colour"],
    ["happy","feeling good"],
    ["heart","body organ"],
    ["house","building for living"],
    ["learn","gain knowledge"],
    ["light","brightness"],
    ["money","medium of exchange"],
    ["month","part of a year"],
    ["mother","female parent"],
    ["music","organized sound"],
    ["night","dark part of day"],
    ["paper","material for writing"],
    ["plant","living thing that grows"],
    ["place","location"],
    ["point","specific position"],
    ["right","correct"],
    ["river","flowing water"],
    ["school","place for learning"],
    ["small","not large"],
    ["speak","talk"],
    ["start","begin"],
    ["story","account of events"],
    ["study","learn"],
    ["table","furniture"],
    ["teach","help someone learn"],
    ["today","this day"],
    ["water","liquid we drink"],
    ["where","asking about location"],
    ["world","earth and its people"],
    ["write","make words on paper"]
  ]

};


/* SHOW LESSON */

function showLesson(id) {

  document.querySelectorAll(".lesson").forEach(section => {
    section.classList.remove("active");
  });

  document.getElementById(id).classList.add("active");

}


/* VOICE */

function speakText(text) {

  if ("speechSynthesis" in window) {

    speechSynthesis.cancel();

    const speech = new SpeechSynthesisUtterance(text);

    speech.lang = "en-US";
    speech.rate = 0.8;
    speech.pitch = 1;

    speechSynthesis.speak(speech);

  } else {

    alert("Voice reading is not supported on this browser.");

  }

}


/* CREATE WORD CARDS */

function createWords(type) {

  const container = document.getElementById(type + "Words");

  container.innerHTML = "";

  words[type].forEach(item => {

    const card = document.createElement("div");

    card.className = "word-card";

    card.innerHTML = `
      <div class="word">${item[0]}</div>
      <div class="meaning">${item[1]}</div>

      <button class="speak"
        onclick="speakText('${item[0]}')">
        🔊 Listen
      </button>
    `;

    container.appendChild(card);

  });

}


/* SEARCH */

function searchWords(type) {

  const input = document.querySelector(
    "#" + type + "Words"
  ).parentElement.querySelector(".search");

  const search = input.value.toLowerCase();

  const cards = document.querySelectorAll(
    "#" + type + "Words .word-card"
  );

  cards.forEach(card => {

    const word = card.querySelector(".word").textContent.toLowerCase();

    if (word.includes(search)) {
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }

  });

}


/* LOAD WORDS */

createWords("two");
createWords("three");
createWords("four");
createWords("five");

</script>

</body>
</html>
