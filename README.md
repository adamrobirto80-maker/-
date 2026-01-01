# -<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>التقويم الأمازيغي</title>
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="mobile-web-app-capable" content="yes">
    <style>
        :root { --blue: #0062cc; --green: #009639; --yellow: #ffd700; --dark: #2c3e50; }
        body { font-family: sans-serif; background-color: #1a1a1a; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; color: white; }
        .app-container { background: white; width: 90%; max-width: 400px; border-radius: 30px; overflow: hidden; box-shadow: 0 20px 50px rgba(0,0,0,0.5); color: #333; }
        .header { background: linear-gradient(135deg, var(--blue), var(--green), var(--yellow)); padding: 40px 20px; text-align: center; }
        .symbol { font-size: 80px; color: #e74c3c; text-shadow: 2px 2px 0px white; }
        .date-box { padding: 40px 20px; text-align: center; }
        .tifinagh { font-size: 2rem; color: var(--green); margin-bottom: 15px; font-weight: bold; }
        .arabic-date { font-size: 1.4rem; color: var(--dark); margin-bottom: 10px; }
        .gregorian { color: #999; font-size: 0.9rem; border-top: 1px solid #eee; pt: 20px; margin-top: 20px; padding-top: 20px; }
        .btn-share { background: var(--blue); color: white; border: none; padding: 10px 20px; border-radius: 50px; margin-top: 20px; cursor: pointer; }
    </style>
</head>
<body>

<div class="app-container">
    <div class="header">
        <div class="symbol">ⵣ</div>
        <h2 style="margin:0; color: white;">Asssegwas Ameggaz</h2>
    </div>
    <div class="date-box">
        <div id="tifinagh" class="tifinagh">...</div>
        <div id="arabic" class="arabic-date">...</div>
        <div id="gregorian" class="gregorian">...</div>
        <button class="btn-share" onclick="window.print()">حفظ التقويم</button>
    </div>
</div>

<script>
    function loadDate() {
        const d = new Date();
        const year = d.getFullYear() + 950;
        const monthsAr = ["ينّاير", "فورار", "ماغرس", "إبرير", "مايو", "يونيو", "يوليو", "غشت", "شتنبر", "كتوبر", "نوانبر", "دوجانبر"];
        const monthsTif = ["ⵢⴻⵏⵏⴰⵢⴻⵔ", "ⴼⵓⵔⴰⵔ", "ⵎⴰⵖⵔⴻⵙ", "ⵉⴱⵔⵉⵔ", "ⵎⴰⵢⵢⵓ", "ⵢⵓⵏⵢⵓ", "ⵢⵓⵍⵢⵓ", "ⵖⵓⵛⵜ", "ⵛⵓⵜⴰⵏⴱⵉⵔ", "ⴽⵜⵓⴱⴻⵔ", "ⵏⵡⴰⵏⴱⵉⵔ", "ⴷⵓⵊⴰⵏⴱⵉⵔ"];
        
        document.getElementById('tifinagh').innerText = d.getDate() + " " + monthsTif[d.getMonth()] + " " + year;
        document.getElementById('arabic').innerText = d.getDate() + " " + monthsAr[d.getMonth()] + " " + year;
        document.getElementById('gregorian').innerText = "الموافق لـ: " + d.toLocaleDateString('ar-MA', {day:'numeric', month:'long', year:'numeric'});
    }
    loadDate();
</script>
</body>
</html>
