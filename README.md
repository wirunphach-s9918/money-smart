<html lang="th">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>MoneySmart P5 - ร้อยละเพื่อความฉลาดรู้ทางการเงิน</title>
  <style>
    body { font-family: system-ui, sans-serif; padding: 16px; max-width: 820px; margin: auto; }
    .card { border: 1px solid #ddd; border-radius: 12px; padding: 14px; margin: 12px 0; }
    label { display: block; margin-top: 8px; }
    input, textarea, button { width: 100%; padding: 10px; margin-top: 6px; border-radius: 10px; border: 1px solid #ccc; }
    button { cursor: pointer; font-weight: 700; }
    .row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
    .out { background: #f7f7f7; padding: 10px; border-radius: 10px; margin-top: 10px; }
  </style>
</head>
<body>

  <h1>MoneySmart P5</h1>
  <p>เว็บแอปคำนวณ <b>ส่วนลด</b> และ <b>การออม</b> ด้วยร้อยละ</p>

  <div class="card">
    <h2>ภารกิจ 1: คำนวณส่วนลด</h2>
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
    <div class="out" id="discountOut">ผลลัพธ์จะแสดงที่นี่</div>
  </div>

  <div class="card">
    <h2>ภารกิจ 2: คำนวณการออม</h2>
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
    <div class="out" id="savingOut">ผลลัพธ์จะแสดงที่นี่</div>
  </div>

  <div class="card">
    <h2>Reflection: เหตุผลของฉัน</h2>
    <label>ฉันตัดสินใจอย่างไร และเพราะอะไร</label>
    <textarea id="reflection" rows="3" placeholder="พิมพ์ 1-2 ประโยค"></textarea>
  </div>

  <script>
    function calcDiscount() {
      // 1) อ่านค่าจาก input
      const price = Number(document.getElementById("price").value);
      const discountPct = Number(document.getElementById("discountPct").value);

      // 2) คำนวณ (สูตรร้อยละ)
      const discountBaht = price * (discountPct / 100);
      const finalPrice = price - discountBaht;

      // 3) แสดงผล
      document.getElementById("discountOut").innerHTML =
        `ส่วนลด = ${discountBaht.toFixed(2)} บาท<br>ราคาหลังลด = ${finalPrice.toFixed(2)} บาท`;
    }

    function calcSaving() {
      const money = Number(document.getElementById("money").value);
      const savePct = Number(document.getElementById("savePct").value);

      const saving = money * (savePct / 100);
      const remain = money - saving;

      document.getElementById("savingOut").innerHTML =
        `เงินออม = ${saving.toFixed(2)} บาท<br>เงินคงเหลือ = ${remain.toFixed(2)} บาท`;
    }
  </script>

</body>
</html>
