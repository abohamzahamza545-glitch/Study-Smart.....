>ط
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#4210a5">
<title>StudySmart - تطبيق الدراسة الذكي</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Tahoma,Arial,sans-serif;
 background:linear-gradient(145deg,#d7edff,#e9d8ff);
 color:#29105f;
}
button,input,select,textarea{font:inherit}
button{cursor:pointer}
.header{
 background:linear-gradient(100deg,#300078,#671bd0);
 color:white;
 border-bottom:8px solid #ffca20;
 padding:17px 12px;
 text-align:center;
}
.header h1{font-size:35px;margin:0}
.header h1 span{color:#ffca20}
.header p{margin:5px 0 0}
.container{max-width:850px;margin:auto;padding:13px}
.panel{
 background:#fffaf0;
 border:4px solid #ffcb27;
 border-radius:23px;
 padding:20px;
 margin:15px 0;
 box-shadow:0 5px 15px #27105b25;
}
h2{text-align:center;color:#48109d}
input,select,textarea{
 display:block;width:100%;padding:13px;
 margin:10px 0;border:2px solid #d9c7f4;
 border-radius:12px;background:white;
}
textarea{min-height:100px;resize:vertical}
.primary{
 background:linear-gradient(100deg,#4710a5,#087be8);
 color:white;border:0;border-radius:13px;
 padding:14px;font-weight:bold;width:100%;
}
.secondary{
 background:#eee5ff;color:#42109b;
 border:2px solid #cbb3f5;border-radius:12px;
 padding:11px;font-weight:bold;
}
.hidden{display:none!important}
.welcome{
 background:linear-gradient(100deg,#44109c,#761bd2);
 color:white;border-radius:16px;
 padding:14px;margin-bottom:14px;
 text-align:center;
}
.welcome strong{color:#ffda32}
.hero{
 background:linear-gradient(120deg,#087ce9,#32d4ef);
 border:5px solid #ffca20;
 border-radius:22px;padding:18px 12px;
 text-align:center;color:white;
 margin-bottom:15px;
}
.hero .girl{font-size:65px}
.hero h2{color:white;font-size:28px;margin:5px}
.hero p{margin:5px}
.grid{
 display:grid;
 grid-template-columns:repeat(2,minmax(0,1fr));
 gap:12px;
}
.tile{
 border:3px solid white;
 border-radius:20px;
 min-height:137px;
 padding:12px 6px;
 text-align:center;
 color:#27105f;
 box-shadow:0 4px 9px #32105b25;
 display:flex;flex-direction:column;
 align-items:center;justify-content:center;
 gap:7px;font-weight:bold;
}
.tile .emoji{font-size:43px}
.tile span:last-child{font-size:15px}
.purple{background:linear-gradient(#e6caff,#a65cff)}
.blue{background:linear-gradient(#d2f4ff,#45b6ff)}
.green{background:linear-gradient(#e1ffc4,#8ce448)}
.orange{background:linear-gradient(#fff0b6,#ffb52c)}
.pink{background:linear-gradient(#ffd5ed,#ff83c5)}
.cyan{background:linear-gradient(#d4ffff,#55d9db)}
.bottom{
 display:grid;grid-template-columns:repeat(5,1fr);
 gap:3px;background:#4b0eae;
 padding:8px;border-radius:18px;
 margin-top:15px;
}
.bottom button{
 background:transparent;color:white;border:0;
 padding:9px 2px;font-size:12px;
}
.bottom b{display:block;font-size:24px;margin-bottom:5px}
.bottom button.active{
 background:#ffca20;color:#32106d;
 border-radius:13px;
}
.section{
 background:white;border:3px solid #e3d5ff;
 border-radius:17px;padding:16px;margin:12px 0;
}
.section h3{color:#4b0eae}
.modal{
 display:none;position:fixed;inset:0;
 background:#14052bd9;z-index:20;
 padding:12px;align-items:center;justify-content:center;
}
.modal.show{display:flex}
.dialog{
 background:#fffaf0;border:4px solid #ffca20;
 border-radius:22px;padding:17px;
 width:100%;max-width:600px;
 max-height:92vh;overflow:auto;
}
.dialog h2{
 background:#4b0eae;color:white;
 border-radius:13px;padding:12px;
}
.close{background:#eee;color:#48109d;border:0;
 padding:9px 14px;border-radius:10px;float:left}
.answer{background:#eee5ff;padding:12px;border-radius:12px;margin-top:12px}
.book-frame{width:100%;height:60vh;border:0}
.small{font-size:12px;color:#66557e}
.stat{background:#f0e5ff;padding:12px;border-radius:12px;margin:8px 0}
footer{text-align:center;color:#51348b;padding:20px}
@media(max-width:390px){
 .grid{gap:8px}
 .tile{min-height:120px}
 .bottom button{font-size:10px}
}
</style>
</head>

<body>

<header class="header">
 <h1>Study<span>Smart</span></h1>
 <p>Your Smart Learning Companion</p>
</header>

<main class="container">

<!-- صفحة التسجيل -->
<section id="register" class="panel">
 <div class="hero">
  <div class="girl">🏆📚</div>
  <h2>أهلاً بك في StudySmart</h2>
  <p>تعلم بذكاء.. حقق نجاحك</p>
 </div>

 <h2>تسجيل الطالب</h2>
 <form id="registerForm">
  <label>اسم الطالب</label>
  <input id="studentName" required placeholder="اكتب اسم الطالب">

  <label>رقم هاتف ولي الأمر</label>
  <input id="parentPhone" required type="tel" placeholder="رقم الهاتف">

  <label>المرحلة الدراسية</label>
  <select id="studentGrade" required>
   <option value="">اختر الصف الدراسي</option>
   <option>الصف الأول الثانوي</option>
   <option>الصف الثاني الثانوي</option>
   <option>الصف الثالث الثانوي</option>
  </select>

  <button class="primary" type="submit">دخول التطبيق 🚀</button>
 </form>
</section>

<!-- لوحة التحكم -->
<section id="dashboard" class="hidden">

 <div class="welcome">
  <strong id="welcomeName">مرحباً بك</strong>
  <div id="welcomeGrade"></div>
  <div>معاً نحو التفوق والنجاح ⭐</div>
 </div>

 <div class="hero">
  <div class="girl">👩🏻‍🎓🏆📖</div>
  <h2>StudySmart</h2>
  <p>Your Smart Learning Companion</p>
  <h3 style="color:white">تعلم بذكاء.. حقق نجاحك</h3>
 </div>

 <div class="grid">

  <button class="tile purple" onclick="openSection('ai')">
   <span class="emoji">🤖</span>
   <span>المعلم الذكي AI</span>
  </button>

  <button class="tile blue" onclick="openSection('lessons')">
   <span class="emoji">📖</span>
   <span>شرح الدروس وكتب الوزارة</span>
  </button>

  <button class="tile green" onclick="openSection('quiz')">
   <span class="emoji">📝</span>
   <span>الأسئلة والاختبارات</span>
  </button>

  <button class="tile orange" onclick="openSection('classwork')">
   <span class="emoji">🏅</span>
   <span>الأداءات الصفية</span>
  </button>

  <button class="tile cyan" onclick="openSection('homework')">
   <span class="emoji">🏠</span>
   <span>الأداءات المنزلية</span>
  </button>

  <button class="tile pink" onclick="openSection('grades')">
   <span class="emoji">🏆</span>
   <span>التقييمات</span>
  </button>

  <button class="tile green" onclick="openSection('reports')">
   <span class="emoji">📊</span>
   <span>التقارير والنتائج</span>
  </button>

  <button class="tile purple" onclick="openSection('monthly')">
   <span class="emoji">🗓️</span>
   <span>الاختبار الشهري</span>
  </button>

 </div>

 <div class="bottom">
  <button onclick="openSection('settings')"><b>⚙️</b>الإعدادات</button>
  <button onclick="openSection('support')"><b>🎧</b>الدعم الفني</button>
  <button class="active" onclick="goHome()"><b>🏠</b>الرئيسية</button>
  <button onclick="openSection('statistics')"><b>📈</b>إحصائياتي</button>
  <button onclick="openSection('parent')"><b>👤</b>ولي الأمر</button>
 </div>

</section>
</main>

<!-- نافذة الأقسام -->
<div class="modal" id="modal">
 <div class="dialog">
  <button class="close" onclick="closeSection()">إغلاق ✕</button>
  <h2 id="modalTitle">StudySmart</h2>
  <div id="modalContent"></div>
 </div>
</div>

<footer>StudySmart © 2026</footer>

<script>
let student="";
let phone="";
let grade="";
let attempts=0;
let correctTotal=0;
let currentScore=0;
let savedTasks=[];
let bookURL="";

const $=id=>document.getElementById(id);

$("registerForm").addEventListener("submit",function(e){
 e.preventDefault();

 student=$("studentName").value.trim();
 phone=$("parentPhone").value.trim();
 grade=$("studentGrade").value;

 if(!student||!phone||!grade){
  alert("من فضلك أكمل جميع البيانات");
  return;
 }

 $("welcomeName").textContent="مرحباً يا "+student+" 👋";
 $("welcomeGrade").textContent=grade;

 $("register").classList.add("hidden");
 $("dashboard").classList.remove("hidden");

 window.scrollTo(0,0);
});

function goHome(){
 $("modal").classList.remove("show");
 $("dashboard").classList.remove("hidden");
 window.scrollTo(0,0);
}

function openSection(page){
 $("dashboard").classList.add("hidden");
 $("modal").classList.add("show");

 let title="";
 let content="";

 if(page==="ai"){
  title="🤖 المعلم الذكي";
  content=`
   <p>أهلاً يا ${escapeHTML(student)}! اسألني عن دروسك.</p>
   <textarea id="aiQuestion" placeholder="اكتب سؤالك هنا..."></textarea>
   <button class="primary" onclick="askTeacher()">إرسال السؤال</button>
   <button class="secondary" onclick="startVoice()">🎙️ تحدث بالصوت</button>
   <div class="answer" id="aiAnswer">المعلم الذكي - نسخة تجريبية</div>
   <p class="small">للحصول على إجابات تعليمية حقيقية من الذكاء الاصطناعي يلزم ربط خدمة AI.</p>
  `;
 }

 else if(page==="lessons"){
  title="📚 كتب الوزارة وشرح الدروس";
  content=`
   <div class="section">
    <h3>كتاب الوزارة</h3>
    <p>الصف الحالي: ${escapeHTML(grade)}</p>
    <label>اختاري ملف الكتاب PDF من جهازك:</label>
    <input type="file" id="bookFile" accept=".pdf,application/pdf" onchange="loadBook(this)">
    <div id="bookStatus" class="answer">لم يتم اختيار كتاب بعد.</div>
    <button class="secondary" onclick="showBook()">فتح الكتاب 📖</button>
   </div>
   <div class="section">
    <h3>شرح الدروس</h3>
    <p>يمكن إضافة شرح كل درس وأسئلته بعد إدخال محتوى الكتاب.</p>
   </div>
  `;
 }

 else if(page==="quiz"||page==="monthly"||page==="grades"){
  title=page==="monthly"?"🗓️ الاختبار الشهري":
        page==="grades"?"🏆 التقييمات":"📝 الأسئلة والاختبارات";

  content=`
   <p>اختبار تدريبي تجريبي</p>
   <div class="section">
    <b>1- ما المقصود بالبيانات؟</b>
    <label><input type="radio" name="q1" value="1"> حقائق وأرقام ورموز</label>
    <label><input type="radio" name="q1" value="0"> نتائج نهائية فقط</label>
    <label><input type="radio" name="q1" value="0"> لا شيء مما سبق</label>
   </div>
   <div class="section">
    <b>2- ما فائدة المعلومات؟</b>
    <label><input type="radio" name="q2" value="1"> المساعدة على الفهم واتخاذ القرار</label>
    <label><input type="radio" name="q2" value="0"> منع التعلم</label>
    <label><input type="radio" name="q2" value="0"> ليس لها فائدة</label>
   </div>
   <div class="section">
    <b>3- ما الذي يساعد على التعلم؟</b>
    <label><input type="radio" name="q3" value="1"> القراءة والتدريب</label>
    <label><input type="radio" name="q3" value="0"> عدم المراجعة</label>
   </div>
   <button class="primary" onclick="correctQuiz()">تصحيح الاختبار</button>
   <div class="answer" id="quizResult">أجب عن الأسئلة ثم اضغط تصحيح.</div>
   <p class="small">أسئلة توضيحية تجريبية وليست أسئلة وزارية رسمية.</p>
  `;
 }

 else if(page==="classwork"||page==="homework"){
  title=page==="classwork"?"🏅 الأداءات الصفية":"🏠 الأداءات المنزلية";
  content=`
   <div class="section">
    <h3>النشاط الأول</h3>
    <p>اشرح الفرق بين البيانات والمعلومات بأسلوبك.</p>
    <textarea id="taskAnswer" placeholder="اكتب إجابتك هنا..."></textarea>
    <button class="primary" onclick="saveTask()">حفظ الإجابة</button>
    <div id="taskStatus"></div>
   </div>
   <div class="section">
    <h3>نشاط إضافي</h3>
    <p>اكتب ثلاثة أمثلة على استخدام التكنولوجيا في التعليم.</p>
    <textarea id="taskExtra" placeholder="اكتب إجابتك..."></textarea>
   </div>
  `;
 }

 else if(page==="reports"||page==="statistics"){
  title="📊 التقارير والإحصائيات";
  content=`
   <div class="stat">اسم الطالب: ${escapeHTML(student)}</div>
   <div class="stat">الصف: ${escapeHTML(grade)}</div>
   <div class="stat">عدد الاختبارات: ${attempts}</div>
   <div class="stat">مجموع الإجابات الصحيحة: ${correctTotal}</div>
   <div class="stat">الإجابات المحفوظة: ${savedTasks.length}</div>
   <p>هذه إحصائيات جلسة العرض الحالية.</p>
  `;
 }

 else if(page==="parent"){
  title="👨‍👩‍👧 حساب ولي الأمر";
  content=`
   <div class="section">
    <h3>بيانات الطالب</h3>
    <p>اسم الطالب: ${escapeHTML(student)}</p>
    <p>الصف: ${escapeHTML(grade)}</p>
    <p>رقم ولي الأمر: ${escapeHTML(phone)}</p>
   </div>
   <div class="section">
    <h3>متابعة المستوى</h3>
    <p>عدد الاختبارات: ${attempts}</p>
    <p>الإجابات الصحيحة: ${correctTotal}</p>
   </div>
   <p class="small">هذه شاشة عرض تجريبية. لا يوجد إرسال تقارير أو رسائل فعلية لولي الأمر بعد.</p>
  `;
 }

 else if(page==="settings"){
  title="⚙️ الإعدادات";
  content=`
   <div class="section">
    <p>مرحباً ${escapeHTML(student)}</p>
    <button class="secondary" onclick="logout()">تسجيل الخروج</button>
   </div>
  `;
 }

 else if(page==="support"){
  title="🎧 الدعم الفني";
  content=`
   <p>اكتب استفسارك أو ملاحظتك:</p>
   <textarea id="supportMessage" placeholder="اكتب رسالتك هنا"></textarea>
   <button class="primary" onclick="sendSupport()">حفظ الرسالة التجريبية</button>
   <div id="supportStatus"></div>
  `;
 }

 $("modalTitle").textContent=title;
 $("modalContent").innerHTML=content;
}

function closeSection(){
 $("modal").classList.remove("show");
 $("dashboard").classList.remove("hidden");
}

function logout(){
 $("modal").classList.remove("show");
 $("dashboard").classList.add("hidden");
 $("register").classList.remove("hidden");
 $("registerForm").reset();
 window.scrollTo(0,0);
}

function escapeHTML(s){
 return String(s).replace(/[&<>"']/g,function(c){
  return {"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c];
 });
}

function loadBook(input){
 const file=input.files[0];
 if(!file)return;

 if(file.type!=="application/pdf"){
  alert("من فضلك اختاري ملف PDF");
  return;
 }

 if(bookURL)URL.revokeObjectURL(bookURL);
 bookURL=URL.createObjectURL(file);
 $("bookStatus").textContent="تم اختيار الكتاب: "+file.name;
}

function showBook(){
 if(!bookURL){
  alert("اختاري كتاب PDF أولاً");
  return;
 }
 $("modalContent").innerHTML=`
  <button class="secondary" onclick="openSection('lessons')">العودة</button>
  <iframe class="book-frame" src="${bookURL}"></iframe>
 `;
}

function correctQuiz(){
 let score=0;
 for(let i=1;i<=3;i++){
  const selected=document.querySelector('input[name="q'+i+'"]:checked');
  if(!selected){
   $("quizResult").textContent="من فضلك أجب عن جميع الأسئلة.";
   return;
  }
  score+=Number(selected.value);
 }
 attempts++;
 currentScore=score;
 correctTotal+=score;
 $("quizResult").textContent="نتيجتك: "+score+" من 3 ⭐";
}

function saveTask(){
 const value=$("taskAnswer").value.trim();
 if(!value){
  $("taskStatus").textContent="اكتب إجابتك أولاً.";
  return;
 }
 savedTasks.push(value);
 $("taskStatus").textContent="تم حفظ الإجابة في جلسة العرض بنجاح.";
}

function askTeacher(){
 const question=$("aiQuestion").value.trim();
 if(!question){
  $("aiAnswer").textContent="اكتب سؤالك أولاً.";
  return;
 }
 const answer="وصل سؤالك: "+question+
 ". هذه نسخة تجريبية من المعلم الذكي. لشرح الدرس والإجابة عن أسئلة الكتاب تلقائياً يجب ربط التطبيق بخدمة ذكاء اصطناعي.";
 $("aiAnswer").textContent=answer;
 speak(answer);
}

function startVoice(){
 const Recognition=window.SpeechRecognition||window.webkitSpeechRecognition;
 if(!Recognition){
  $("aiAnswer").textContent="التعرف على الصوت غير مدعوم في هذا المتصفح. يمكنك كتابة السؤال.";
  return;
 }
 const recognition=new Recognition();
 recognition.lang="ar-EG";
 recognition.onresult=function(event){
  $("aiQuestion").value=event.results[0][0].transcript;
 };
 recognition.onerror=function(){
  $("aiAnswer").textContent="لم نتمكن من التقاط الصوت. حاولي مرة أخرى.";
 };
 recognition.start();
}

function speak(text){
 if(!("speechSynthesis" in window))return;
 speechSynthesis.cancel();
 const utterance=new SpeechSynthesisUtterance(text);
 utterance.lang="ar-EG";
 speechSynthesis.speak(utterance);
}

function sendSupport(){
 const message=$("supportMessage").value.trim();
 if(!message){
  $("supportStatus").textContent="اكتبي الرسالة أولاً.";
  return;
 }
 $("supportStatus").textContent="تم تسجيل الرسالة في العرض التجريبي.";
}
</script>

</body>
</html>
