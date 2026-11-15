
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>StudySmart</title>

<style>
:root {
  --purple:#4816b5;
  --deep:#24106c;
  --blue:#078af4;
  --gold:#ffca19;
  --pink:#ed4eae;
}
* {box-sizing:border-box}
body {
  margin:0;
  font-family:Tahoma,Arial,sans-serif;
  background:linear-gradient(140deg,#291078,#087ff0);
  min-height:100vh;
  color:#29105c;
}
button,input,select,textarea {font:inherit}
button {cursor:pointer}
.page {
  width:min(100%,560px);
  margin:auto;
  padding:16px;
}
.card {
  background:#fffaf0;
  border:5px solid var(--gold);
  border-radius:25px;
  padding:22px;
  box-shadow:0 8px 20px #16004c55;
}
.logo {
  text-align:center;
  color:white;
  font-size:34px;
  font-weight:bold;
  margin:20px 0;
  text-shadow:2px 3px 5px #16004c;
}
.logo span {color:var(--gold)}
.subtitle {
  text-align:center;
  color:#fff;
  margin-bottom:20px;
}
h2 {color:var(--purple);text-align:center}
.field {margin:14px 0}
.field label {display:block;font-weight:bold;margin-bottom:7px}
.field input,.field select {
  width:100%;
  padding:13px;
  border:2px solid #d7c4f6;
  border-radius:13px;
  background:white;
}
.main-btn {
  width:100%;
  padding:14px;
  border:0;
  border-radius:15px;
  color:white;
  background:linear-gradient(100deg,#4714b5,#087ef1);
  font-weight:bold;
  margin-top:12px;
}
.note {font-size:12px;color:#66577b;line-height:1.7}
#dashboard {display:none}
.screen {
  width:100%;
  position:relative;
}
.screen img {
  width:100%;
  display:block;
  height:auto;
  border-radius:5px;
}
.hotspot {
  position:absolute;
  background:transparent;
  border:0;
  border-radius:18%;
}
.hotspot:focus-visible {
  outline:3px solid white;
}
#ai {left:58%;top:12%;width:20%;height:12%}
#lessons {left:80%;top:12%;width:19%;height:12%}
#quizzes {left:58%;top:26%;width:20%;height:11%}
#classwork {left:80%;top:26%;width:19%;height:11%}
#homework {left:58%;top:39%;width:20%;height:11%}
#grades {left:80%;top:39%;width:19%;height:11%}
#reports {left:58%;top:52%;width:20%;height:11%}
#monthly {left:80%;top:52%;width:19%;height:11%}
#settings {left:1%;top:88%;width:20%;height:10%}
#support {left:22%;top:88%;width:19%;height:10%}
#home {left:41%;top:86%;width:19%;height:12%}
#stats {left:61%;top:88%;width:18%;height:10%}
#parent {left:80%;top:88%;width:19%;height:10%}

#modal {
  display:none;
  position:fixed;
  inset:0;
  background:#120638bb;
  z-index:10;
  padding:18px;
  align-items:center;
  justify-content:center;
}
.modal-card {
  width:min(100%,460px);
  max-height:88vh;
  overflow:auto;
  background:#fff;
  border:4px solid var(--gold);
  border-radius:22px;
  padding:17px;
}
.modal-title {
  background:linear-gradient(100deg,#4011a8,#087ef1);
  color:white;
  border-radius:14px;
  padding:15px;
  text-align:center;
}
.modal-card input,.modal-card textarea {
  width:100%;
  padding:12px;
  margin:8px 0;
  border:1px solid #c7b3ed;
  border-radius:10px;
}
.action {
  padding:11px 15px;
  background:var(--purple);
  color:white;
  border:0;
  border-radius:10px;
  margin:5px 2px;
}
.result {
  padding:13px;
  background:#f0eaff;
  border-radius:12px;
  margin-top:12px;
  line-height:1.8;
}
#pdfViewer {
  width:100%;
  height:55vh;
  border:1px solid #ccc;
}
</style>
</head>

<body>

<!-- تسجيل الطالب -->
<section id="login" class="page">

  <div class="logo">Study<span>Smart</span></div>
  <div class="subtitle">Your Smart Learning Companion</div>

  <div class="card">
    <h2>أهلاً بك في StudySmart</h2>
    <p style="text-align:center">سجّل بياناتك لبدء رحلة التعلم</p>

    <form id="registerForm">

      <div class="field">
        <label>اسم الطالب</label>
        <input id="studentName" required
        placeholder="اكتب اسم الطالب">
      </div>

      <div class="field">
        <label>رقم هاتف ولي الأمر</label>
        <input id="guardianPhone" type="tel"
        required placeholder="رقم الهاتف">
      </div>

      <div class="field">
        <label>المرحلة الدراسية</label>
        <select id="grade" required>
          <option value="">اختار الصف الدراسي</option>
          <option value="أولى ثانوي">الصف الأول الثانوي</option>
          <option value="ثانية ثانوي">الصف الثاني الثانوي</option>
          <option value="ثالثة ثانوي">الصف الثالث الثانوي</option>
        </select>
      </div>

      <button class="main-btn" type="submit">
        تسجيل الدخول
      </button>

      <p class="note">
        هذا نموذج تجريبي. لا تدخلي بيانات شخصية حقيقية
        قبل إضافة نظام تسجيل آمن وحماية للبيانات.
      </p>
    </form>
  </div>
</section>

<!-- لوحة التحكم الأصلية -->
<section id="dashboard" class="page">

  <div class="screen">

    <!-- ارفعي صورة لوحة التحكم الأصلية باسم dashboard.png -->
    <img src="dashboard.png" alt="StudySmart Dashboard">

    <button class="hotspot" id="ai" aria-label="المعلم الذكي"
    onclick="openSection('ai')"></button>

    <button class="hotspot" id="lessons" aria-label="شرح الدروس"
    onclick="openSection('lessons')"></button>

    <button class="hotspot" id="quizzes" aria-label="الاختبارات"
    onclick="openSection('quizzes')"></button>

    <button class="hotspot" id="classwork" aria-label="الأداءات الصفية"
    onclick="openSection('classwork')"></button>

    <button class="hotspot" id="homework" aria-label="الأداءات المنزلية"
    onclick="openSection('homework')"></button>

    <button class="hotspot" id="grades" aria-label="التقييمات"
    onclick="openSection('grades')"></button>

    <button class="hotspot" id="reports" aria-label="التقارير"
    onclick="openSection('reports')"></button>

    <button class="hotspot" id="monthly" aria-label="الاختبار الشهري"
    onclick="openSection('monthly')"></button>

    <button class="hotspot" id="settings" aria-label="الإعدادات"
    onclick="openSection('settings')"></button>

    <button class="hotspot" id="support" aria-label="الدعم الفني"
    onclick="openSection('support')"></button>

    <button class="hotspot" id="home" aria-label="الرئيسية"
    onclick="openSection('home')"></button>

    <button class="hotspot" id="stats" aria-label="إحصائياتي"
    onclick="openSection('stats')"></button>

    <button class="hotspot" id="parent" aria-label="ولي الأمر"
    onclick="openSection('parent')"></button>

  </div>
</section>

<!-- نافذة الأقسام -->
<div id="modal">
  <div class="modal-card">
    <h2 class="modal-title" id="modalTitle"></h2>
    <div id="modalContent"></div>
    <button class="action" onclick="closeSection()">إغلاق</button>
  </div>
</div>

<script>
let student = {};

document.getElementById("registerForm")
.addEventListener("submit",function(e) {
  e.preventDefault();

  student.name =
    document.getElementById("studentName").value;

  student.phone =
    document.getElementById("guardianPhone").value;

  student.grade =
    document.getElementById("grade").value;

  document.getElementById("login").style.display="none";
  document.getElementById("dashboard").style.display="block";
});

const sections = {
  ai: "المعلم الذكي AI",
  lessons: "شرح الدروس وكتب الوزارة",
  quizzes: "الأسئلة والاختبارات",
  classwork: "الأداءات الصفية",
  homework: "الأداءات المنزلية",
  grades: "التقييمات",
  reports: "التقارير والنتائج",
  monthly: "الاختبار الشهري",
  settings: "الإعدادات",
  support: "الدعم الفني",
  home: "الرئيسية",
  stats: "إحصائياتي",
  parent: "حساب ولي الأمر"
};

function openSection(id) {
  document.getElementById("modalTitle").textContent =
    sections[id];

  let html = "";

  if(id==="ai") {
    html = `
      <p>أهلاً ${student.name}، أنا المعلم الذكي.</p>
      <p>اكتب سؤالك عن الدرس:</p>
      <textarea id="question" placeholder="اكتب سؤالك"></textarea>
      <button class="action" onclick="askAI()">إرسال</button>
      <button class="action" onclick="voiceAI()">🎤 تحدث معي</button>
      <div class="result" id="answer">في انتظار سؤالك.</div>
    `;
  }

  if(id==="lessons") {
    html = `
      <h3>كتب الوزارة</h3>
      <p>المرحلة: ${student.grade}</p>
      <p>اختاري ملف الكتاب الدراسي PDF:</p>
      <input type="file" id="bookFile" accept=".pdf">
      <div id="bookStatus" class="result">
        لم يتم اختيار كتاب بعد.
      </div>
      <div id="pdfArea"></div>
    `;
  }

  if(id==="quizzes" || id==="grades" || id==="monthly") {
    html = `
      <h3>اختبار المعلومات والوسائط</h3>
      <p>وفق موضوعات كتاب أولى ثانوي المرفوع.</p>
      <p>ما المقصود بالبيانات؟</p>
      <label><input type="radio" name="quiz" value="a">
      حقائق تمثل بالأرقام أو الأحرف أو الرموز</label><br>
      <label><input type="radio" name="quiz" value="b">
      معلومات تم تحليلها وتنظيمها</label><br>
      <label><input type="radio" name="quiz" value="c">
      وسيلة لنقل المعلومات</label><br>
      <button class="action" onclick="checkQuiz()">تصحيح الإجابة</button>
      <div class="result" id="quizResult">
        اختاري الإجابة.
      </div>
    `;
  }

  if(id==="classwork") {
    html = `
      <h3>الأداءات الصفية</h3>
      <p>اكتبي إجابتك عن نشاط الدرس.</p>
      <textarea placeholder="الإجابة"></textarea>
      <button class="action" onclick="alert('تم تسجيل الإجابة في النموذج التجريبي')">
      حفظ الإجابة</button>
    `;
  }

  if(id==="homework") {
    html = `
      <h3>الأداءات المنزلية</h3>
      <textarea placeholder="اكتبي حل الواجب"></textarea>
      <button class="action" onclick="alert('تم تسجيل الواجب تجريبياً')">
      إرسال الواجب</button>
    `;
  }

  if(id==="reports" || id==="stats") {
    html = `
      <h3>تقرير الطالب</h3>
      <p>اسم الطالب: ${student.name}</p>
      <p>الصف: ${student.grade}</p>
      <p>الاختبارات المكتملة: 0</p>
      <p>الواجبات المسلمة: 0</p>
      <p>متوسط الدرجات: —</p>
    `;
  }

  if(id==="parent") {
    html = `
      <h3>متابعة ولي الأمر</h3>
      <p>اسم الطالب: ${student.name}</p>
      <p>المرحلة: ${student.grade}</p>
      <p>رقم ولي الأمر: ${student.phone}</p>
      <p>ستظهر النتائج والواجبات هنا بعد ربط قاعدة البيانات.</p>
    `;
  }

  if(id==="settings") {
    html = `
      <p>اسم الطالب: ${student.name}</p>
      <p>المرحلة الدراسية: ${student.grade}</p>
    `;
  }

  if(id==="support") {
    html = `
      <p>الدعم الفني لتطبيق StudySmart</p>
      <textarea placeholder="اكتب رسالتك"></textarea>
      <button class="action" onclick="alert('نموذج تجريبي')">إرسال</button>
    `;
  }

  if(id==="home") {
    html = `<p>أهلاً بك في StudySmart يا ${student.name}.</p>`;
  }

  document.getElementById("modalContent").innerHTML=html;
  document.getElementById("modal").style.display="flex";

  const file=document.getElementById("bookFile");

  if(file) {
    file.addEventListener("change",function() {
      const selected=this.files[0];
      if(!selected) return;

      document.getElementById("bookStatus").textContent =
        selected.name;

      const url=URL.createObjectURL(selected);

      document.getElementById("pdfArea").innerHTML =
        `<iframe id="pdfViewer" title="كتاب الوزارة"></iframe>`;

      document.getElementById("pdfViewer").src=url;
    });
  }
}

function closeSection() {
  document.getElementById("modal").style.display="none";
}

function checkQuiz() {
  const selected=document.querySelector(
    'input[name="quiz"]:checked'
  );

  const result=document.getElementById("quizResult");

  if(!selected) {
    result.textContent="اختاري إجابة أولاً.";
    return;
  }

  result.textContent =
    selected.value==="a"
    ? "إجابة صحيحة! أحسنتِ."
    : "حاولي مرة أخرى. راجعي تعريف البيانات في الدرس.";

}

function askAI() {
  const q=document.getElementById("question").value.trim();
  const answer=document.getElementById("answer");

  if(!q) {
    answer.textContent="اكتبي سؤالك أولاً.";
    return;
  }

  answer.textContent =
    "استقبل النموذج سؤالك: "+q+
    "\nللحصول على شرح حقيقي مخصص للسؤال يجب ربط خدمة ذكاء اصطناعي.";
}

function voiceAI() {
  const answer=document.getElementById("answer");

  const Recognition =
    window.SpeechRecognition ||
    window.webkitSpeechRecognition;

  if(!Recognition) {
    answer.textContent="المتصفح لا يدعم التعرف على الصوت.";
    return;
  }

  const recognition=new Recognition();
  recognition.lang="ar-EG";
  recognition.start();

  recognition.onresult=function(event) {
    const spoken=event.results[0][0].transcript;
    document.getElementById("question").value=spoken;
    answer.textContent="سمعت سؤالك: "+spoken+
      "\nاضغطي إرسال لتمريره للنموذج.";
  };

  recognition.onerror=function() {
    answer.textContent="تعذر تشغيل الميكروفون. تحققي من إذن المتصفح.";
  };
}

</script>
</body>
</html>
