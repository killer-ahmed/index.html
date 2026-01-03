<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>KCR Sistem</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: black;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: monospace;
  color: #00ff88;
}

.kutu {
  background: rgba(0,0,0,0.9);
  padding: 25px;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 0 25px #00ff88;
  width: 340px;
}

input {
  width: 90%;
  padding: 10px;
  margin-top: 10px;
  border-radius: 8px;
  border: none;
  outline: none;
}

button {
  margin: 8px;
  padding: 10px 25px;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  font-size: 15px;
  background: #00ff88;
  color: black;
}

#log {
  margin-top: 15px;
  text-align: left;
  font-size: 14px;
  min-height: 120px;
}

#soru, #galeri {
  display: none;
}
</style>
</head>

<body>

<div class="kutu" id="panel">
  <h3>KCR KONTROL PANELİ</h3>

  <input type="text" id="user" placeholder="Instagram adını yaz">

  <br>
  <button onclick="basla()">BAŞLAT</button>

  <div id="log"></div>

  <div id="soru">
    <p>
      Bilgilerinizin <b>Killer</b> ile<br>
      paylaşılmasına izin veriliyor mu?
    </p>
    <button onclick="izinEvet()">EVET</button>
    <button onclick="izinHayir()">HAYIR</button>
  </div>
</div>

<div class="kutu" id="galeri">
  <h3>HACKER ZONE</h3>
  <img src="https://i.imgur.com/3ZQ3Z5p.jpg" width="100%" style="margin-bottom:10px;">
  <img src="https://i.imgur.com/0KFBHTB.jpg" width="100%">
</div>

<script>
function basla(){
  const user = document.getElementById("user").value;
  const log = document.getElementById("log");

  if(user.trim() === ""){
    alert("Instagram adını gir");
    return;
  }

  log.innerHTML =
    ">> Sistem başlatılıyor...<br>" +
    ">> Kullanıcı bulundu<br>" +
    ">> Ad: " + user + "<br>" +
    ">> Yetkiler kontrol ediliyor...<br>" +
    ">> Onay bekleniyor...";

  document.getElementById("soru").style.display = "block";
}

function izinEvet(){
  const log = document.getElementById("log");

  log.innerHTML +=
    "<br><span style='color:red'>>> Veri aktarılıyor...</span>";

  setTimeout(() => {
    log.innerHTML +=
      "<br>>> Onay alındı ✔" +
      "<br>>> Hoş geldin Killer’in adamı 😈";
  }, 1500);
}

function izinHayir(){
  document.getElementById("panel").style.display = "none";
  document.getElementById("galeri").style.display = "block";
}
</script>

</body>
</html>
