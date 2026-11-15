
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#4211a5">
<title>StudySmart</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Tahoma,Arial;
 background:linear-gradient(140deg,#25076d,#078cf1);
 color:#28105c;
}
header{
 background:#4211a5;
 color:white;
 text-align:center;
 padding:18px;
 border-bottom:7px solid #ffca19;
}
header h1{font-size:36px;margin:5px}
header h1 span{color:#ffca19}
header p{margin:5px}
.container{max-width:650px;margin:auto;padding:14px}
.panel{
 background:#fff8e9;
 border:5px solid #ffca19;
 border-radius:24px;
 padding:18px;
 margin:15px 0;
 box-shadow:0 7px 20px #16004455;
}
h2{text-align:center;color:#4211a5}
input,select,textarea{
 width:100%;
 padding:13px;
 margin:7px 0;
 border:2px solid #d6c4f4;
 border-radius:12px;
 font:inherit;
}
button{
 border:0;
 padding:12px;
 border-radius:13px;
 background:linear-gradient(100deg,#4211a5,#087fe8);
 color:white;
 font-weight:bold;
 font-size:15px;
 cursor:pointer;
}
button:active{transform:scale(.98)}
.wide{width:100%;margin-top:10px}
.hidden{display:none!important}
.dashboard{
 width:100%;
 position:relative;
 overflow:hidden;
 border-radius:15px;
 line-height:0;
}
.dashboard img{width:100%;display:block}
.hot{
 position:absolute;
 background:transparent;
 border:2px solid transparent;
 border-radius:15px;
 padding:0;
}
.hot:focus{border:3px solid white}
#ai{left:59%;top:13%;width:19%;height:15%}
#lessons{left:79%;top:13%;width:19%;height:15%}
#quiz{left:59%;top:29%;width:19%;height:15%}
#classwork{left:79%;top:29%;width:19%;height:15%}
#homework{left:59%;top:44%;width:19%;height:15%}
#grades{left:79%;top:44%;width:19%;height:15%}
#reports{left:59%;top:59%;width:19%;height:15%}
#monthly{left:79%;top:59%;width:19%;height:15%}
#settings{left:0;top:90%;width:20%;height:10%}
#support{left:21%;top:90%;width:19%;height:10%}
#home{left:41%;top:88%;width:19%;height:12%}
#stats{left:61%;top:90%;width:18%;height:10%}
#parent{left:80%;top:90%;width:20%;height:10%}
.modal{
 display:none;
 position:fixed;
 inset:0;
 background:#10052ddd;
 z-index:10;
 padding:12px;
 align-items:center;
 justify-content:center;
}
.modal.show{display:flex}
.dialog{
 background:white;
 border:5px solid #ffca19;
 border-radius:20px;
 padding:17px;
 width:100%;
 max-width:520px;
 max-height:90vh;
 overflow:auto;
}
.dialog h2{
 background:#4211a5;
 color:white;
 padding:12px;
 border-radius:12px;
}
.close{float:left;background:#eee;color:#4211a5}
.tile{
 background:#f1eaff;
 border-radius:12px;
 padding:13px;
 margin:10px 0;
 line-height:1.8;
}
iframe{width:100%;height:65vh;border:0}
footer{text-align:center;color:white;padding:15px;font-size:12px}
</style>
</head>

<body>

<header>
<h1>Study<span>Smart</span></h1>
<p>Your Smart Learning Companion</p>
</header>

<div class="container">

<section id="register" class="panel">
<h2>أهلاً بك في StudySmart</h2>
<p>سجل بياناتك لبدء رحلة التعلم</p>

<form id="registration">
<label>اسم الطالب</label>
<input id="student" required placeholder="اسم الطالب">

<label>رقم هاتف ولي الأمر</label>
<input id="phone" type="tel" required placeholder="رقم ولي الأمر">

<label>المرحلة الدراسية</label>
<select id="grade" required>
<option value="">اختار الصف</option>
<option>أولى ثانوي</option>
<option>ثانية ثانوي</option>
<option>ثالثة ثانوي</option>
</select>

<button class="wide">دخول التطبيق</button>
</form>
</section>

<section id="mainApp" class="hidden">

<div class="dashboard">
<img src="dashboard.png" alt="لوحة تحكم StudySmart">

<button class="hot" id="ai" onclick="openPage('ai')"></button>
<button class="hot" id="lessons" onclick="openPage('lessons')"></button>
<button class="hot" id="quiz" onclick="openPage('quiz')"></button>
<button class="hot" id="classwork" onclick="openPage('classwork')"></button>
<button class="hot" id="homework" onclick="openPage('homework')"></button>
<button class="hot" id="grades" onclick="openPage('grades')"></button>
<button class="hot" id="reports" onclick="openPage('reports')"></button>
<button class="hot" id="monthly" onclick="openPage('monthly')"></button>
<button class="hot" id="settings" onclick="openPage('settings')"></button>
<button class="hot" id="support" onclick="openPage('support')"></button>
<button class="hot" id="home" onclick="openPage('home')"></button>
<button class="hot" id="stats" onclick="openPage('stats')"></button>
<button class="hot" id="parent" onclick="openPage('parent')"></button>
</div>

</section>
</div>

<div id="modal" class="modal">
<div class="dialog">
<button class="close" onclick="closePage()">إغلاق ✕</button>
<h2 id="title"></h2>
<div id="content"></div>
</div>
</div>

<footer>StudySmart © Your Smart Learning Companion</footer>

<script>
let studentName="";
let studentPhone="";
let studentGrade="";
let attempts=0;
let totalScore=0;

document.getElementById("registration")
.addEventListener("submit",function(e){
 e.preventDefault();

 studentName=document.getElementById("student").value;
 studentPhone=document.getElementById("phone").value;
 studentGrade=document.getElementById("grade").value;

 document.getElementById("register").classList.add("hidden");
 document.getElementById("mainApp").classList.remove("hidden");
});

function openPage(page){
 let title="";
 let html="";

 if(page==="lessons"){
 title="كتب الوزارة وشرح الدروس";
 html=studentGrade==="أولى ثانوي"?
 `<div class="tile">
 <h3>كتاب البرمجة والذكاء الاصطناعي</h3>
 <p>الصف الأول الثانوي</p>
 <button class="wide" onclick="openBook()">فتح كتاب الوزارة PDF 📖</button>
 </div>`:
 `<div class="tile">كتاب هذا الصف سيضاف في مرحلة التوسع القادمة. الكتاب المتاح حاليًا هو كتاب أولى ثانوي.</div>`;
 }

 if(page==="ai"){
 title="المعلم الذكي AI";
 html=`
 <p>أهلاً ${safe(studentName)}، اسأل عن درسك.</p>
 <textarea id="question" placeholder="اكتب سؤالك هنا"></textarea>
 <button onclick="askAI()">إرسال السؤال</button>
 <button onclick="voiceInput()">🎙️ تحدث</button>
 <div class="tile" id="answer">المعلم الذكي - نسخة تجريبية</div>`;
 }

 if(page==="quiz"||page==="grades"||page==="monthly"){
 title="الأسئلة والاختبارات";
 html=`
 <div class="tile">
 <b>السؤال الأول: ما المقصود بالبيانات؟</b><br>
 <label><input type="radio" name="q1" value="1"> حقائق وأرقام ورموز</label><br>
 <label><input type="radio" name="q1" value="0"> نتائج نهائية فقط</label>
 </div>
 <div class="tile">
 <b>السؤال الثاني: ما فائدة المعلومات؟</b><br>
 <label><input type="radio" name="q2" value="1"> المساعدة في فهم واتخاذ القرار</label><br>
 <label><input type="radio" name="q2" value="0"> منع التعلم</label>
 </div>
 <button onclick="checkQuiz()">تصحيح الاختبار</button>
 <div class="tile" id="result">اختار إجاباتك أولاً</div>
 <p>اختبار تجريبي وليس تقييمًا وزاريًا رسميًا.</p>`;
 }

 if(page==="homework"||page==="classwork"){
 title=page==="homework"?"الأداءات المنزلية":"الأداءات الصفية";
 html=`
 <div class="tile">نشاط: اشرح الفرق بين البيانات والمعلومات.</div>
 <textarea id="work" placeholder="اكتب إجابتك"></textarea>
 <button onclick="saveWork()">حفظ الإجابة</button>
 <div id="workResult"></div>`;
 }

 if(page==="reports"||page==="stats"){
 title="التقارير والإحصائيات";
 html=`
 <div class="tile">
 الطالب: ${safe(studentName)}<br>
 الصف: ${safe(studentGrade)}<br>
 الاختبارات: ${attempts}<br>
 الإجابات الصحيحة: ${totalScore}
 </div>`;
 }

 if(page==="parent"){
 title="حساب ولي الأمر";
 html=`
 <div class="tile">
 اسم الطالب: ${safe(studentName)}<br>
 الصف: ${safe(studentGrade)}<br>
 رقم ولي الأمر: ${safe(studentPhone)}
 </div>
 <p>هذه بيانات عرض محلية، ولا يوجد اتصال فعلي بحساب ولي الأمر.</p>`;
 }

 if(page==="settings"){
 title="الإعدادات";
 html=`<div class="tile">إعدادات StudySmart</div>
 <button onclick="location.reload()">تسجيل خروج</button>`;
 }

 if(page==="support"){
 title="الدعم الفني";
 html=`<textarea id="message" placeholder="اكتب رسالتك"></textarea>
 <button onclick="document.getElementById('supportResult').textContent='تم تسجيل الرسالة في العرض.'">إرسال</button>
 <div id="supportResult"></div>`;
 }

 if(page==="home"){
 title="الرئيسية";
 html=`أهلاً ${safe(studentName)} في StudySmart`;
 }

 show(title,html);
}

function show(title,html){
 document.getElementById("title").textContent=title;
 document.getElementById("content").innerHTML=html;
 document.getElementById("modal").classList.add("show");
}

function closePage(){
 document.getElementById("modal").classList.remove("show");
}

function openBook(){
 show("كتاب الوزارة",
 `<p>كتاب البرمجة والذكاء الاصطناعي - أولى ثانوي</p>
 <iframe src="book.pdf" title="كتاب الوزارة"></iframe>
 <a href="book.pdf" target="_blank">فتح الكتاب في نافذة جديدة</a>`);
}

function checkQuiz(){
 let a=document.querySelector('input[name="q1"]:checked');
 let b=document.querySelector('input[name="q2"]:checked');
 if(!a||!b){
 document.getElementById("result").textContent="أجب عن السؤالين أولاً";
 return;
 }
 let n=Number(a.value)+Number(b.value);
 attempts++;
 totalScore+=n;
 document.getElementById("result").textContent=
 "درجتك: "+n+" من 2";
}

function askAI(){
 let q=document.getElementById("question").value;
 let a=document.getElementById("answer");
 if(!q.trim()){a.textContent="اكتب سؤالك أولاً";return}
 a.textContent="هذه نسخة عرض تجريبية. يمكن ربط المعلم الذكي بخدمة ذكاء اصطناعي لاحقًا. اسأل عن محتوى الكتاب بعد إضافة خدمة المعلم الذكي.";
 speak(a.textContent);
}

function voiceInput(){
 const R=window.SpeechRecognition||window.webkitSpeechRecognition;
 if(!R){
 document.getElementById("answer").textContent="التعرف الصوتي غير مدعوم في هذا المتصفح.";
 return;
 }
 const r=new R();
 r.lang="ar-EG";
 r.onresult=e=>{
 document.getElementById("question").value=e.results[0][0].transcript;
 };
 r.start();
}

function speak(text){
 if("speechSynthesis" in window){
 let u=new SpeechSynthesisUtterance(text);
 u.lang="ar-EG";
 speechSynthesis.speak(u);
 }
}

function saveWork(){
 let value=document.getElementById("work").value;
 document.getElementById("workResult").textContent=
 value.trim()?"تم حفظ الإجابة في جلسة العرض.":"اكتب الإجابة أولاً";
}

function safe(s){
 return String(s).replace(/[&<>"']/g,c=>({
 "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
 }[c]));
}
</script>
</body>
</html>
