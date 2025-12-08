# Docrepository-
<!doctype html>
<html lang="en">
<head>x
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Gentle Moments Captions</title>
  <style>
    body{font-family:system-ui;padding:24px;max-width:720px;margin:auto}
    .card{border:1px solid #eee;padding:18px;border-radius:10px;box-shadow:0 4px 14px rgba(0,0,0,0.05)}
    .caption{white-space:pre-wrap;margin:12px 0;font-size:18px;line-height:1.5}
    button{padding:8px 12px;border-radius:8px;border:1px solid #bbb;background:#fff;cursor:pointer}
  </style>
</head>
<body>
  <h1>Gentle Moments Captions</h1>
  <div class="card">
    <div id="caption" class="caption">Loading...</div>
    <button id="randomBtn">Random</button>
    <button id="copyBtn">Copy</button>
  </div>

<script>
const caps = [
  "Sometimes the quiet moments say the most",
  "Beauty is always here you just need to notice it",
  "Growth begins the moment you decide to slow down",
  "Soft days are still progress",
  "You are allowed to restart as many times as you need"
];

function randomCaption(){
  return caps[Math.floor(Math.random()*caps.length)];
}

const captionEl = document.getElementById('caption');
const randomBtn = document.getElementById('randomBtn');
const copyBtn = document.getElementById('copyBtn');

captionEl.textContent = randomCaption();

randomBtn.onclick = ()=> captionEl.textContent = randomCaption();

copyBtn.onclick = async()=>{
  await navigator.clipboard.writeText(captionEl.textContent);
  copyBtn.textContent = "Copied";
  setTimeout(()=> copyBtn.textContent="Copy",1000);
};
</script>
</body>
</html>
