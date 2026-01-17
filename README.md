<!doctype html>
<html lang="th">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>💖 MoneySmart P5 - ร้อยละเพื่อความฉลาดรู้ทางการเงิน 💖</title>
  <style>
    body {
      font-family: 'Prompt', sans-serif;
      background: linear-gradient(135deg, #ffe6f2, #e6f7ff);
      padding: 20px;
      max-width: 860px;
      margin: auto;
      color: #444;
    }

    h1 {
      text-align: center;
      color: #ff66b2;
      text-shadow: 2px 2px #fff;
      font-size: 2.2em;
      margin-bottom: 10px;
    }

    p {
      text-align: center;
      font-size: 1.1em;
      color: #666;
      margin-bottom: 30px;
    }

    .card {
      background: #fff;
      border-radius: 20px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
      padding: 20px 24px;
      margin: 20px 0;
      transition: transform 0.2s ease;
    }

    .card:hover {
      transform: translateY(-4px);
    }

    h2 {
      color: #ff80bf;
      border-left: 6px solid #ffb3d9;
      padding-left: 10px;
      font-size: 1.4em;
    }

    label {
      display: block;
      margin-top: 10px;
      font-weight: 600;
      color: #555;
    }

    input, textarea, button {
      width: 100%;
      padding: 10px;
      margin-top: 6px;
      border-radius: 12px;
      border: 1px solid #ddd;
      font-size: 1em;
      transition: 0.3s;
    }

    input:focus, textarea:focus {
      border-color: #ff99cc;
      outline: none;
      box-shadow: 0 0 6px #ffb3d9;
    }

    button {
      background: linear-gradient(135deg, #ff99cc, #ff66b2);
      color: white;
      font-weight: 700;
      border: none;
      margin-top: 14px;
      cursor: pointer;
      box-shadow: 0 3px 8px rgba(255,102,178,0.3);
      transition: 0.3s;
    }

    button:hover {
      background: linear-gradient(135deg, #ff66b2, #ff3385);
      transform: scale(1.03);
    }

    .row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 14px;
    }

    .out {
      background: #fdf2f8;
      padding: 12px;
      border-radius: 12px;
      margin-top: 12px;
      color: #333;
      border: 1px dashed #ffb3d9;
      font-weight: 500;
    }

    footer {
      text-align: center;
      margin-top: 30px;
      color: #888;
      font-size: 0.9em;
    }

    .emoji {
      font-size: 1.4em;
    }
  </style>
</head>
<body>

  <h1>💖 MoneySmart P5 💖</h1>
  <p>เว็บแอปคำนวณ <b>ส่วนลด</b> และ <b>การออม</b> ด้วยร้อยละ<br>เรียนรู้การเงินอย่างสนุกและมีสไตล์ ✨</p>

  <div class="card">
    <h2>ภารกิจ 1: คำนวณส่วนลด 🛍️</h2>
    <div class="row">
      <div>
        <label>ราคาสินค้า (บาท)</label>
        <input id="price" type="number" placeholder="เช่น 200" />
      </div>
      <div>
        <label>ส่วนลด (%)</label>
        <input id="discountPct" type="number" placeholder="เช่น 15" />
      </div>
    </div>
    <button onclick="calcDiscount()">คำนวณส่วนลด</button>
    <div class="out" id="discountOut">ผลลัพธ์จะแสดงที่นี่ 💡</div>
  </div>

  <div class="card">
    <h2>ภารกิจ 2: คำนวณการออม 💰</h2>
    <div class="row">
      <div>
        <label>เงินทั้งหมด (บาท)</label>
        <input id="money" type="number" placeholder="เช่น 300" />
      </div>
      <div>
        <label>ออม (%)</label>
        <input id="savePct" type="number" placeholder="เช่น 20" />
      </div>
    </div>
    <button onclick="calcSaving()">คำนวณการออม</button>
    <div class="out" id="savingOut">ผลลัพธ์จะแสดงที่นี่ 💡</div>
  </div>

  <div class="card">
    <h2>Reflection: เหตุผลของฉัน 💭</h2>
    <label>ฉันตัดสินใจอย่างไร และเพราะอะไร</label>
    <textarea id="reflection" rows="3" placeholder="พิมพ์ 1-2 ประโยค เช่น ฉันเลือกออมเพราะอยากมีเงินสำรอง..."></textarea>
  </div>

  <footer>สร้างด้วย 💕 เพื่อการเรียนรู้ทางการเงินอย่างชาญฉลาด</footer>

  <script>
    function calcDiscount() {
      const price = Number(document.getElementById("price").value);
      const discountPct = Number(document.getElementById("discountPct").value);

      if (!price || !discountPct) {
        document.getElementById("discountOut").innerHTML = "⚠️ กรุณากรอกข้อมูลให้ครบก่อนคำนวณ";
        return;
      }

      const discountBaht = price * (discountPct / 100);
      const finalPrice = price - discountBaht;

      document.getElementById("discountOut").innerHTML =
        `🎀 ส่วนลด = <b>${discountBaht.toFixed(2)}</b> บาท<br>💸 ราคาหลังลด = <b>${finalPrice.toFixed(2)}</b> บาท`;
    }

    function calcSaving() {
      const money = Number(document.getElementById("money").value);
      const savePct = Number(document.getElementById("savePct").value);

      if (!money || !savePct) {
        document.getElementById("savingOut").innerHTML = "⚠️ กรุณากรอกข้อมูลให้ครบก่อนคำนวณ";
        return;
      }

      const saving = money * (savePct / 100);
      const remain = money - saving;

      document.getElementById("savingOut").innerHTML =
        `💖 เงินออม = <b>${saving.toFixed(2)}</b> บาท<br>💵 เงินคงเหลือ = <b>${remain.toFixed(2)}</b> บาท`;
    }
  </script>

</body>
</html>


