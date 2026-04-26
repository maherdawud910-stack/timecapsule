<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>Time Capsule Dashboard</title>
</head>

<body style="font-family:Arial;text-align:center;background:#0f172a;color:white;padding:30px;">

  <h1>⏳ Time Capsule</h1>

  <!-- عرض المحتوى -->
  <div id="output" style="margin:20px;padding:20px;background:#1e293b;border-radius:10px;">
    لا يوجد محتوى بعد
  </div>

  <!-- لوحة التحكم -->
  <h2>لوحة التحكم</h2>

  <input id="textInput" placeholder="اكتب رسالتك هنا"
    style="padding:10px;width:250px;border-radius:8px;border:none;">

  <br><br>

  <button onclick="saveText()"
    style="padding:10px 20px;border:none;border-radius:8px;background:#38bdf8;cursor:pointer;">
    حفظ
  </button>

  <button onclick="clearText()"
    style="padding:10px 20px;border:none;border-radius:8px;background:#ef4444;cursor:pointer;">
    حذف
  </button>

  <script>
    // تحميل النص عند فتح الصفحة
    window.onload = function() {
      let saved = localStorage.getItem("capsuleText");
      if (saved) {
        document.getElementById("output").innerText = saved;
      }
    }

    function saveText() {
      let text = document.getElementById("textInput").value;
      document.getElementById("output").innerText = text;
      localStorage.setItem("capsuleText", text);
    }

    function clearText() {
      localStorage.removeItem("capsuleText");
      document.getElementById("output").innerText = "لا يوجد محتوى بعد";
    }
  </script>

</body>
</html>
