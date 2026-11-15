
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#4211a5">
<title>StudySmart</title>

<style>
:root{
--purple:#4211a5;
--blue:#078ff4;
--gold:#ffca19;
--cream:#fff8e9;
}
*{box-sizing:border-box}
body{
margin:0;
font-family:Tahoma,Arial,sans-serif;
background:linear-gradient(145deg,#25076d,#078cf1);
color:#28105c
}
button,input,select,textarea{font:inherit}
button{cursor:pointer}
.wrap{width:min(100%,760px);margin:auto;padding:12px}
.brand{
text-align:center;color:white;
font-size:40px;font-weight:bold;margin:8px
}
.brand span{color:var(--gold)}
.panel{
background:var(--cream);
border:5px solid var(--gold);
border-radius:24px;
padding:18px;
box-shadow:0 8px 24px #16004455
}
.panel h1,.panel h2{text-align:center;color:var(--purple)}
.login-logo{
display:flex;justify-content:center;margin:10px
}
.login-logo img{
width:125px;height:125px;
object-fit:contain;border-radius:25px;
border:3px solid var(--gold)
}
.app-brand{
display:flex;align-items:center;
justify-content:center;gap:10px
}
.app-brand img{
width:55px;height:55px;object-fit:contain
}
.field{margin:12px 0}
.field label{display:block;font-weight:bold;margin-bottom:6px}
.field input,.field select{
width:100%;padding:13px;
border:2px solid #d8c6f5;
border-radius:12px;background:white
}
.primary{
background:linear-gradient(100deg,var(--purple),var(--blue));
color:white;border:0;border-radius:13px;
padding:13px 18px;font-weight:bold
}
.wide{width:100%;margin-top:12px}
.hidden{display:none!important}
.muted,.small{font-size:12px;line-height:1.7;color:#655777}
.dash{
position:relative;width:100%;
overflow:hidden;border-radius:14px;
background:white;line-height:0
}
.dash img{display:block;width:100%;height:auto}
.hot{
position:absolute;border:2px solid transparent;
background:transparent;border-radius:16px;
padding:0;z-index:2
}
.hot:focus-visible{
outline:4px solid white;
background:#ffffff30
}
/* أماكن الأزرار فوق صورة لوحة التحكم */
#h-ai{left:47.5%;top:13.2%;width:16.5%;height:14.5%}
#h-lessons{left:64.5%;top:13.2%;width:16%;height:14.5%}
#h-quiz{left:47.5%;top:28.8%;width:16.5%;height:14.3%}
#h-class{left:64.5%;top:28.8%;width:16%;height:14.3%}
#h-homework{left:47.5%;top:43.5%;width:16.5%;height:14.3%}
#h-grades{left:64.5%;top:43.5%;width:16%;height:14.3%}
#h-reports{left:47.5%;top:58%;width:16.5%;height:14.3%}
#h-monthly{left:64.5%;top:58%;width:16%;height:14.3%}
#h-settings{left:1%;top:90%;width:20%;height:9%}
#h-support{left:22%;top:90%;width:19%;height:9%}
#h-home{left:42%;top:88%;width:18%;height:11%}
#h-stats{left:61%;top:90%;width:18%;height:9%}
#h-parent{left:80%;top:90%;width:19%;height:9%}

.menu{
display:grid;
grid-template-columns:repeat(2,minmax(0,1fr));
gap:9px;margin-top:12px
}
.menu button{
border:2px solid #e6d7ff;
border-radius:14px;padding:13px 8px;
background:linear-gradient(145deg,#fff,#f0e8ff);
color:var(--purple);font-weight:bold;
min-height:60px
}
.footer{text-align:center;color:white;font-size:12px;padding:14px}
.modal{
position:fixed;inset:0;background:#10052ddd;
z-index:20;display:none;
align-items:center;justify-content:center;padding:12px
}
.modal.show{display:flex}
.dialog{
width:min(100%,560px);max-height:92vh;
overflow:auto;background:white;
border:5px solid var(--gold);
border-radius:22px;padding:16px
}
.dialog h2{
background:linear-gradient(100deg,var(--purple),var(--blue));
color:white;padding:12px;border-radius:12px;
text-align:center
}
.close{
float:left;border:0;border-radius:10px;
padding:8px 12px;color:var(--purple);
background:#eee5ff
}
.tile,.question{
background:#f4efff;border:1px solid #ddcefa;
border-radius:13px;padding:12px;margin:10px 0;
line-height:1.8
}
.dialog input,.dialog textarea{
width:100%;padding:11px;
border:1px solid #c9b7eb;border-radius:10px;margin:6px 0
}
.dialog iframe{width:100%;height:65vh;border:1px solid #ddd}
.action{
border:0;border-radius:10px;padding:10px 14px;
background:var(--purple);color:white;margin:4px
}
.secondary{
border:0;border-radius:10px;padding:10px 14px;
background:#eae2fa;color:var(--purple);margin:4px
}
.answer{display:block;margin:8px 0}
.answer input{width:auto!important}
a{color:#174cbb}
</style>
</head>

<body>
<main class="wrap">

<div class="app-brand">
<img src="assets/app-icon.png" alt="StudySmart">
<div class="brand">Study<span>Smart</span></div>
</div>

<p style="text-align:center;color:white">
Your Smart Learning Companion
</p>

<!-- تسجيل الطالب -->
<section id="register" class="panel">

<div class="login-logo">
<img src="assets/app-icon.png" alt="StudySmart">
</div>

<h1>أهلاً بك في StudySmart</h1>
<p style="text-align:center">تعلم بذكاء.. حقق نجاحك</p>

<form id="loginForm">

<div class="field">
<label>اسم الطالب</label>
<input id="student" required maxlength="60" placeholder="اسم الطالب">
</div>

<div class="field">
<label>رقم هاتف ولي الأمر</label>
<input id="guardian" type="tel" required placeholder="رقم ولي الأمر">
</div>

<div class="field">
<label>الصف الدراسي</label>
<select id="grade" required>
<option value="">اختاري الصف</option>
<option>أولى ثانوي</option>
<option>ثانية ثانوي</option>
<option>ثالثة ثانوي</option>
</select>
</div>

<button class="primary wide" type="submit">
دخول التطبيق 🚀
</button>

</form>
<p class="muted">نسخة تجريبية للعرض.</p>
</section>

<!-- لوحة التحكم -->
<section id="app" class="hidden">

<div class="dash">

<img src="assets/dashboard.png"
alt="لوحة تحكم StudySmart"
onerror="this.alt='تعذر تحميل صورة لوحة التحكم'">

<button class="hot" id="h-ai" aria-label="المعلم الذكي"
onclick="openSection('ai')"></button>

<button class="hot" id="h-lessons" aria-label="شرح الدروس"
onclick="openSection('lessons')"></button>

<button class="hot" id="h-quiz" aria-label="الاختبارات"
onclick="openSection('quiz')"></button>

<button class="hot" id="h-class" aria-label="الأداءات الصفية"
onclick="openSection('classwork')"></button>

<button class="hot" id="h-homework" aria-label="الأداءات المنزلية"
onclick="openSection('homework')"></button>

<button class="hot" id="h-grades" aria-label="التقييمات"
onclick="openSection('grades')"></button>

<button class="hot" id="h-reports" aria-label="التقارير"
onclick="openSection('reports')"></button>

<button class="hot" id="h-monthly" aria-label="الاختبار الشهري"
onclick="openSection('monthly')"></button>

<button class="hot" id="h-settings" aria-label="الإعدادات"
onclick="openSection('settings')"></button>

<button class="hot" id="h-support" aria-label="الدعم"
onclick="openSection('support')"></button>

<button class="hot" id="h-home" aria-label="الرئيسية"
onclick="openSection('home')"></button>

<button class="hot" id="h-stats" aria-label="الإحصائيات"
onclick="openSection('stats')"></button>

<button class="hot" id="h-parent" aria-label="ولي الأمر"
onclick="openSection('parent')"></button>

</div>

<!-- أزرار بديلة تضمن سهولة فتح الأقسام -->
<div class="menu">
<button onclick="openSection('ai')">🤖 المعلم الذكي AI</button>
<button onclick="openSection('lessons')">📖 كتب الوزارة</button>
<button onclick="openSection('quiz')">📝 الأسئلة والاختبارات</button>
<button onclick="openSection('classwork')">🏅 الأداءات الصفية</button>
<button onclick="openSection('homework')">🏠 الأداءات المنزلية</button>
<button onclick="openSection('grades')">🏆 التقييمات</button>
<button onclick="openSection('reports')">📊 التقارير والنتائج</button>
<button onclick="openSection('monthly')">🗓️ الاختبار الشهري</button>
<button onclick="openSection('stats')">📈 إحصائياتي</button>
<button onclick="openSection('parent')">👨‍👩‍👧 حساب ولي الأمر</button>
<button onclick="openSection('support')">🎧 الدعم الفني</button>
<button onclick="openSection('settings')">⚙️ الإعدادات</button>
</div>

<p class="footer">
StudySmart - كتاب البرمجة والذكاء الاصطناعي
للصف الأول الثانوي
</p>

</section>
</main>

<!-- نافذة الأقسام -->
<div id="modal" class="modal">
<div class="dialog">
<button class="close" onclick="closeModal()">إغلاق ✕</button>
<h2 id="modalTitle"></h2>
<div id="modalBody"></div>
</div>
</div>

<script>
'use strict';

let profile={name:'',phone:'',grade:''};
let score=0,attempts=0;
const $=id=>document.getElementById(id);

const safe=s=>String(s).replace(/[&<>"']/g,c=>({
'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'
}[c]));

$("loginForm").addEventListener("submit",function(e){
e.preventDefault();

const name=$("student").value.trim();
const phone=$("guardian").value.trim();
const grade=$("grade").value;

if(!name||!phone||!grade){
alert("من فضلك أكملي البيانات");
return;
}

profile={name,phone,grade};

$("register").classList.add("hidden");
$("app").classList.remove("hidden");

window.scrollTo(0,0);
});

const titles={
ai:'المعلم الذكي AI',
lessons:'شرح الدروس وكتب الوزارة',
quiz:'الأسئلة والاختبارات',
classwork:'الأداءات الصفية',
homework:'الأداءات المنزلية',
grades:'التقييمات',
reports:'التقارير والنتائج',
monthly:'الاختبار الشهري',
settings:'الإعدادات',
support:'الدعم الفني',
home:'الرئيسية',
stats:'إحصائياتي',
parent:'حساب ولي الأمر'
};

function show(title,html){
$("modalTitle").textContent=title;
$("modalBody").innerHTML=html;
$("modal").classList.add("show");
}

function closeModal(){
$("modal").classList.remove("show");
}

function openSection(id){
let html='';

if(id==='lessons'){
html=profile.grade==='أولى ثانوي'?
`
<div class="tile">
<h3>كتاب الوزارة</h3>
<p>
البرمجة والذكاء الاصطناعي<br>
مقدمة في تكنولوجيا المعلومات والاتصالات<br>
الصف الأول الثانوي 2025–2026
</p>
<button class="primary" onclick="showBook()">
📖 فتح الكتاب كاملًا
</button>
<p>
<a href="books/book.pdf" target="_blank">
فتح الكتاب في نافذة جديدة
</a>
</p>
</div>
`:
`<div class="tile">
الكتاب المتاح حاليًا هو كتاب الصف الأول الثانوي فقط.
</div>`;
}

if(['quiz','grades','monthly'].includes(id)){
html=profile.grade==='أولى ثانوي'?
`
<p>تقييم تدريبي من درس المعلومات والوسائط.</p>

<div class="question">
<b>1- البيانات (Data) هي:</b>
<label class="answer">
<input type="radio" name="q1" value="a">
حقائق تُمثل بالأرقام أو الأحرف أو الرموز
</label>
<label class="answer">
<input type="radio" name="q1" value="b">
معلومات تم تحليلها وتنظيمها
</label>
</div>

<div class="question">
<b>2- المعلومات (Information) هي:</b>
<label class="answer">
<input type="radio" name="q2" value="a">
معنى أو قيمة للمتلقي وتستخدم لاتخاذ القرار
</label>
<label class="answer">
<input type="radio" name="q2" value="b">
وسيلة لتخزين الملفات فقط
</label>
</div>

<div class="question">
<b>3- المعرفة (Knowledge) هي:</b>
<label class="answer">
<input type="radio" name="q3" value="a">
معلومات تم تحليلها وتنظيمها للمساعدة في حل المشكلات
</label>
<label class="answer">
<input type="radio" name="q3" value="b">
حقائق غير منظمة
</label>
</div>

<div class="question">
<b>4- أي مما يلي ليس من خصائص المعلومات؟</b>
<label class="answer">
<input type="radio" name="q4" value="a"> الاستمرارية
</label>
<label class="answer">
<input type="radio" name="q4" value="b"> قابلية التكرار
</label>
<label class="answer">
<input type="radio" name="q4" value="c"> أن لها شكلاً مادياً ثابتاً
</label>
<label class="answer">
<input type="radio" name="q4" value="d"> الانتشار
</label>
</div>

<div class="question">
<b>5- التلفزيون يصنف ضمن:</b>
<label class="answer">
<input type="radio" name="q5" value="a"> وسائط التعبير
</label>
<label class="answer">
<input type="radio" name="q5" value="b"> وسائط النقل والإرسال
</label>
<label class="answer">
<input type="radio" name="q5" value="c"> وسائط التسجيل
</label>
</div>

<div class="question">
<b>6- الثقافة الإعلامية هي القدرة على:</b>
<label class="answer">
<input type="radio" name="q6" value="a">
تفسير المعلومات التي تم الحصول عليها من الوسائط بدقة
</label>
<label class="answer">
<input type="radio" name="q6" value="b">
تخزين كل المعلومات على الهاتف
</label>
</div>

<button class="primary" onclick="gradeQuiz()">
تصحيح التقييم
</button>

<div id="quizResult" class="tile">
اختاري الإجابات ثم اضغطي تصحيح.
</div>

<p class="small">
أسئلة تدريبية من محتوى الصفحتين 8 و9،
وليست تقييمًا وزاريًا رسميًا.
</p>
`:
`<div class="tile">
الكتاب المتاح حاليًا للصف الأول الثانوي فقط.
</div>`;
}

if(id==='ai'){
html=`
<p>أهلاً ${safe(profile.name)}! اسألي عن دروسك.</p>
<textarea id="ask" rows="3" placeholder="اكتبي سؤالك"></textarea>
<button class="action" onclick="answerDemo()">إرسال السؤال</button>
<button class="secondary" onclick="listenQuestion()">🎙️ تحدثي بالسؤال</button>
<div id="aiAnswer" class="tile">
المعلم الذكي - نسخة تجريبية.
</div>
`;
}

if(id==='classwork'||id==='homework'){
html=`
<p>نشاط من درس المعلومات والوسائط.</p>
<div class="tile">
اشرحي الفرق بين البيانات والمعلومات والمعرفة.
</div>
<textarea id="workAnswer" rows="4" placeholder="اكتبي إجابتك"></textarea>
<button class="primary" onclick="saveWork()">حفظ الإجابة</button>
<div id="workStatus"></div>
`;
}

if(id==='reports'||id==='stats'){
html=`
<div class="tile">
اسم الطالب: ${safe(profile.name)}<br>
الصف: ${safe(profile.grade)}<br>
عدد الاختبارات: ${attempts}<br>
مجموع الإجابات الصحيحة: ${score}
</div>
`;
}

if(id==='parent'){
html=`
<div class="tile">
اسم الطالب: ${safe(profile.name)}<br>
الصف: ${safe(profile.grade)}<br>
رقم ولي الأمر: ${safe(profile.phone)}
</div>
<p class="small">
حساب ولي الأمر في هذه النسخة شاشة عرض تجريبية.
</p>
`;
}

if(id==='settings'){
html=`
<div class="tile">إعدادات الحساب التجريبي</div>
<button class="secondary" onclick="location.reload()">
تسجيل الخروج
</button>
`;
}

if(id==='support'){
html=`
<p>الدعم الفني</p>
<textarea id="supportMsg" rows="3" placeholder="اكتبي ملاحظتك"></textarea>
<button class="primary" onclick="sendSupport()">إرسال</button>
<div id="supportStatus"></div>
`;
}

if(id==='home'){
html=`<div class="tile">أهلاً ${safe(profile.name)} في StudySmart!</div>`;
}

show(titles[id]||'StudySmart',html);
}

function showBook(){
show('كتاب الوزارة — البرمجة والذكاء الاصطناعي',`
<p>الصف الأول الثانوي - 2025–2026</p>
<iframe
title="كتاب الوزارة PDF"
src="books/book.pdf">
</iframe>
<p>
<a href="books/book.pdf" target="_blank">
فتح الكتاب في نافذة جديدة
</a>
</p>
`);
}

function gradeQuiz(){
const keys=['q1','q2','q3','q4','q5','q6'];
const correct={q1:'a',q2:'a',q3:'a',q4:'c',q5:'b',q6:'a'};

const values=keys.map(k=>
document.querySelector('input[name="'+k+'"]:checked')
);

if(values.some(v=>!v)){
$("quizResult").textContent="أجيبي عن الأسئلة الستة أولاً.";
return;
}

const result=values.reduce((n,v,i)=>
n+(v.value===correct[keys[i]]?1:0),0);

score+=result;
attempts++;

$("quizResult").textContent=
"درجتك "+result+" من 6 ⭐ "+
(result===6?"ممتاز!":"راجعي الدرس وحاولي مرة أخرى.");
}

function answerDemo(){
const q=$("ask").value.trim();
if(!q){
$("aiAnswer").textContent="اكتبي سؤالك أولاً.";
return;
}

const answer=
"وفقًا لدرس المعلومات والوسائط: البيانات حقائق تُمثل بالأرقام أو الأحرف أو الرموز. المعلومات لها معنى أو قيمة للمتلقي وتساعد على اتخاذ القرار. المعرفة معلومات تم تحليلها وتنظيمها للمساعدة في حل المشكلات.";

$("aiAnswer").textContent=answer;
speak(answer);
}

function listenQuestion(){
const R=window.SpeechRecognition||window.webkitSpeechRecognition;

if(!R){
$("aiAnswer").textContent="التعرف الصوتي غير مدعوم في هذا المتصفح.";
return;
}

const r=new R();
r.lang="ar-EG";
r.onresult=e=>{
$("ask").value=e.results[0][0].transcript;
};
r.start();
}

function speak(text){
if('speechSynthesis' in window){
speechSynthesis.cancel();
const u=new SpeechSynthesisUtterance(text);
u.lang='ar-EG';
speechSynthesis.speak(u);
}
}

function saveWork(){
const value=$("workAnswer").value.trim();
$("workStatus").textContent=value?
"تم حفظ الإجابة في جلسة العرض.":
"اكتبي الإجابة أولاً.";
}

function sendSupport(){
const value=$("supportMsg").value.trim();
$("supportStatus").textContent=value?
"تم تسجيل الملاحظة في العرض التجريبي.":
"اكتبي الملاحظة أولاً.";
}

$("modal").addEventListener("click",e=>{
if(e.target===$("modal"))closeModal();
});
</script>
</body>
</html>
