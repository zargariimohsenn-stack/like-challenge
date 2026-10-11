<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>سامانه ثبت حضور</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;600;700;800&display=swap');

:root{
    --bg:#08090d;
    --card:#11131a;
    --card2:#171a22;
    --border:#262a35;
    --text:#f5f5f7;
    --muted:#8f95a3;
    --primary:#7657ff;
    --primary2:#957fff;
    --green:#26d17f;
    --red:#ff5868;
    --orange:#ffb454;
}

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    font-family:"Vazirmatn",Tahoma,sans-serif;
    background:
        radial-gradient(circle at 90% 0%,rgba(118,87,255,.13),transparent 30%),
        radial-gradient(circle at 0% 100%,rgba(38,209,127,.05),transparent 25%),
        var(--bg);
    color:var(--text);
    min-height:100vh;
}

button,input,select{
    font-family:inherit;
}

.container{
    width:min(1150px,92%);
    margin:auto;
}

/* HEADER */

header{
    padding:28px 0 20px;
    border-bottom:1px solid var(--border);
}

.logo{
    display:flex;
    align-items:center;
    gap:13px;
}

.logo-icon{
    width:46px;
    height:46px;
    border-radius:13px;
    background:linear-gradient(135deg,var(--primary),#4930c7);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:21px;
    box-shadow:0 10px 30px rgba(118,87,255,.25);
}

.logo h1{
    font-size:20px;
    font-weight:800;
}

.logo span{
    display:block;
    color:var(--muted);
    font-size:12px;
    margin-top:2px;
}

/* NAV */

.nav{
    display:flex;
    gap:8px;
    margin-top:23px;
    flex-wrap:wrap;
}

.nav button{
    background:var(--card);
    color:var(--muted);
    border:1px solid var(--border);
    padding:10px 17px;
    border-radius:10px;
    cursor:pointer;
    transition:.2s;
}

.nav button:hover,
.nav button.active{
    background:var(--primary);
    color:white;
    border-color:var(--primary);
}

/* SECTIONS */

.section{
    display:none;
    padding:35px 0 80px;
}

.section.active{
    display:block;
}

.title{
    margin-bottom:24px;
}

.title h2{
    font-size:27px;
    margin-bottom:7px;
}

.title p{
    color:var(--muted);
    font-size:13px;
}

/* FORM */

.form-card{
    background:rgba(17,19,26,.92);
    border:1px solid var(--border);
    border-radius:20px;
    padding:25px;
}

.grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px;
}

.field{
    display:flex;
    flex-direction:column;
    gap:8px;
}

.field.full{
    grid-column:1/-1;
}

label{
    color:#c9ccd5;
    font-size:13px;
}

input,
select{
    width:100%;
    background:#0b0d12;
    border:1px solid var(--border);
    color:white;
    padding:14px;
    border-radius:11px;
    outline:none;
    transition:.2s;
}

input:focus,
select:focus{
    border-color:var(--primary);
    box-shadow:0 0 0 3px rgba(118,87,255,.1);
}

/* PEOPLE */

.people{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
}

.person-box{
    background:#0b0d12;
    border:1px solid var(--border);
    padding:18px;
    border-radius:13px;
}

.person-box strong{
    display:block;
    margin-bottom:12px;
}

.counter{
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.counter button{
    width:38px;
    height:38px;
    border-radius:9px;
    border:1px solid var(--border);
    background:var(--card2);
    color:white;
    font-size:20px;
    cursor:pointer;
}

.counter span{
    font-size:22px;
    font-weight:700;
}

/* SUBMIT */

.submit{
    width:100%;
    margin-top:23px;
    border:0;
    border-radius:12px;
    padding:15px;
    background:linear-gradient(135deg,var(--primary),#5b40dc);
    color:white;
    font-size:15px;
    font-weight:700;
    cursor:pointer;
    box-shadow:0 12px 30px rgba(118,87,255,.2);
}

.submit:hover{
    filter:brightness(1.1);
}

/* STATS */

.stats{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:15px;
    margin-bottom:25px;
}

.stat{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:16px;
    padding:20px;
}

.stat span{
    color:var(--muted);
    font-size:13px;
}

.stat strong{
    display:block;
    font-size:27px;
    margin-top:8px;
}

/* DAYS */

.days{
    display:grid;
    grid-template-columns:repeat(5,1fr);
    gap:15px;
}

.day{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:16px;
    padding:18px;
}

.day h3{
    font-size:16px;
    margin-bottom:12px;
}

.day-number{
    font-size:25px;
    font-weight:800;
}

.day small{
    color:var(--muted);
}

.progress{
    height:7px;
    background:#242733;
    border-radius:10px;
    overflow:hidden;
    margin:14px 0 8px;
}

.progress div{
    height:100%;
    width:0;
    background:linear-gradient(90deg,var(--primary),var(--primary2));
    border-radius:10px;
    transition:.4s;
}

.full-text{
    font-size:11px;
    color:var(--muted);
}

/* RECORDS */

.search{
    margin-bottom:17px;
}

.records{
    display:flex;
    flex-direction:column;
    gap:12px;
}

.record{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:15px;
    padding:18px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:15px;
}

.record-info h3{
    margin-bottom:6px;
    font-size:16px;
}

.record-info p{
    color:var(--muted);
    font-size:12px;
    line-height:1.9;
}

.record-actions{
    display:flex;
    gap:7px;
    flex-shrink:0;
}

.small-btn{
    border:1px solid var(--border);
    background:var(--card2);
    color:white;
    border-radius:9px;
    padding:9px 12px;
    cursor:pointer;
}

.small-btn:hover{
    border-color:var(--primary);
}

.delete{
    color:#ff7580;
}

.empty{
    text-align:center;
    padding:50px;
    color:var(--muted);
    background:var(--card);
    border:1px dashed var(--border);
    border-radius:15px;
}

/* RECEIPT */

.receipt-box{
    max-width:550px;
    margin:auto;
}

.receipt{
    background:#11131a;
    border:1px solid var(--border);
    border-radius:20px;
    overflow:hidden;
}

.receipt-top{
    padding:25px;
    text-align:center;
    background:linear-gradient(135deg,#171425,#11131a);
    border-bottom:1px dashed #343846;
}

.receipt-icon{
    font-size:35px;
    margin-bottom:8px;
}

.receipt-top h2{
    font-size:21px;
}

.receipt-top p{
    color:var(--muted);
    font-size:12px;
    margin-top:5px;
}

.receipt-body{
    padding:25px;
}

.receipt-row{
    display:flex;
    justify-content:space-between;
    gap:20px;
    padding:12px 0;
    border-bottom:1px solid #222530;
}

.receipt-row:last-child{
    border-bottom:0;
}

.receipt-row span:first-child{
    color:var(--muted);
}

.receipt-row span:last-child{
    font-weight:600;
}

.tracking{
    margin-top:15px;
    text-align:center;
    background:#0b0d12;
    border:1px dashed var(--primary);
    padding:15px;
    border-radius:12px;
}

.tracking small{
    display:block;
    color:var(--muted);
    margin-bottom:5px;
}

.tracking strong{
    font-size:20px;
    letter-spacing:2px;
}

.receipt-actions{
    display:flex;
    gap:10px;
    margin-top:15px;
}

.receipt-actions button{
    flex:1;
    padding:13px;
    border-radius:11px;
    cursor:pointer;
    border:1px solid var(--border);
    background:var(--card);
    color:white;
}

.receipt-actions button:first-child{
    background:var(--primary);
    border-color:var(--primary);
}

/* RESET */

.reset-area{
    margin-top:60px;
    display:flex;
    justify-content:flex-end;
}

.reset-btn{
    border:0;
    background:transparent;
    color:#666b77;
    font-size:11px;
    cursor:pointer;
    padding:7px;
}

.reset-btn:hover{
    color:var(--red);
}

/* TOAST */

.toast{
    position:fixed;
    left:50%;
    bottom:25px;
    transform:translate(-50%,30px);
    background:#191c25;
    border:1px solid var(--border);
    padding:13px 20px;
    border-radius:12px;
    opacity:0;
    pointer-events:none;
    transition:.3s;
    z-index:9999;
    box-shadow:0 10px 40px rgba(0,0,0,.4);
}

.toast.show{
    opacity:1;
    transform:translate(-50%,0);
}

/* MOBILE */

@media(max-width:800px){

    .stats{
        grid-template-columns:1fr 1fr;
    }

    .days{
        grid-template-columns:1fr 1fr;
    }

    .grid{
        grid-template-columns:1fr;
    }

    .field.full{
        grid-column:auto;
    }

    .record{
        flex-direction:column;
        align-items:stretch;
    }

    .record-actions{
        width:100%;
    }

    .record-actions button{
        flex:1;
    }
}

@media(max-width:500px){

    .container{
        width:94%;
    }

    .section{
        padding-top:25px;
    }

    .stats{
        grid-template-columns:1fr 1fr;
    }

    .days{
        grid-template-columns:1fr;
    }

    .people{
        grid-template-columns:1fr;
    }

    .form-card{
        padding:17px;
    }

    .nav button{
        flex:1;
        font-size:12px;
    }

    .title h2{
        font-size:23px;
    }
}

/* PRINT */

@media print{

    body{
        background:white;
        color:#111;
    }

    header,
    .nav,
    .receipt-actions,
    .reset-area{
        display:none !important;
    }

    .section{
        display:none !important;
    }

    #receiptSection{
        display:block !important;
        padding:0;
    }

    .receipt{
        border:1px solid #ddd;
        color:#111;
    }

    .receipt-top{
        background:white;
    }

    .receipt-row{
        border-color:#ddd;
    }

    .receipt-row span:first-child,
    .receipt-top p,
    .tracking small{
        color:#666;
    }

    .tracking{
        background:#f8f8f8;
        border-color:#777;
    }
}
</style>
</head>

<body>

<header>
<div class="container">

    <div class="logo">
        <div class="logo-icon">✓</div>
        <div>
            <h1>سامانه ثبت حضور</h1>
            <span>مدیریت و ثبت اطلاعات حضور</span>
        </div>
    </div>

    <div class="nav">
        <button class="active" onclick="showSection('register',this)">
            ثبت حضور
        </button>

        <button onclick="showSection('dashboard',this)">
            آمار کلی
        </button>

        <button onclick="showSection('records',this)">
            ثبت‌های من
        </button>

        <button onclick="showSection('receipt',this)">
            آخرین فیش
        </button>
    </div>

</div>
</header>


<main class="container">

<!-- REGISTER -->

<section id="register" class="section active">

<div class="title">
    <h2>ثبت حضور جدید</h2>
    <p>اطلاعات فرد و تعداد همراهان را وارد کنید.</p>
</div>

<div class="form-card">

<div class="grid">

    <div class="field">
        <label>نام و نام خانوادگی</label>
        <input id="name" type="text" placeholder="مثلاً محسن زرگری">
    </div>

    <div class="field">
        <label>شماره همراه</label>
        <input id="phone" type="tel" inputmode="numeric" placeholder="09123456789">
    </div>

    <div class="field full">
        <label>روز حضور</label>

        <select id="day">

            <option value="">
                انتخاب روز
            </option>

            <option value="27">
                ۲۷ آبان
            </option>

            <option value="28">
                ۲۸ آبان
            </option>

            <option value="29">
                ۲۹ آبان
            </option>

            <option value="30">
                ۳۰ آبان
            </option>

            <option value="31">
                ۳۱ آبان
            </option>

        </select>

    </div>

    <div class="field full">

        <label>تعداد افراد</label>

        <div class="people">

            <div class="person-box">

                <strong>👩 خانم</strong>

                <div class="counter">

                    <button onclick="changeCount('women',-1)">−</button>

                    <span id="women">0</span>

                    <button onclick="changeCount('women',1)">+</button>

                </div>

            </div>

            <div class="person-box">

                <strong>👨 آقا</strong>

                <div class="counter">

                    <button onclick="changeCount('men',-1)">−</button>

                    <span id="men">0</span>

                    <button onclick="changeCount('men',1)">+</button>

                </div>

            </div>

        </div>

    </div>

</div>

<button class="submit" onclick="registerPerson()">
    ثبت اطلاعات و صدور فیش
</button>

</div>

</section>


<!-- DASHBOARD -->

<section id="dashboard" class="section">

<div class="title">

    <h2>آمار کلی</h2>

    <p>
        وضعیت ثبت حضور و ظرفیت روزهای مختلف
    </p>

</div>

<div class="stats">

    <div class="stat">
        <span>کل افراد</span>
        <strong id="totalPeople">0</strong>
    </div>

    <div class="stat">
        <span>تعداد خانم</span>
        <strong id="totalWomen">0</strong>
    </div>

    <div class="stat">
        <span>تعداد آقا</span>
        <strong id="totalMen">0</strong>
    </div>

    <div class="stat">
        <span>تعداد ثبت‌ها</span>
        <strong id="totalRecords">0</strong>
    </div>

</div>

<div class="days" id="daysContainer"></div>

</section>


<!-- RECORDS -->

<section id="records" class="section">

<div class="title">

    <h2>ثبت‌های من</h2>

    <p>
        تمام اطلاعات ثبت‌شده در این مرورگر
    </p>

</div>

<div class="search">

    <input
        id="search"
        type="text"
        placeholder="جستجو بر اساس نام، شماره یا کد پیگیری..."
        oninput="renderRecords()"
    >

</div>

<div id="recordsContainer" class="records"></div>

<div class="reset-area">

    <button class="reset-btn" onclick="resetAll()">
        ⚙ ریست اطلاعات
    </button>

</div>

</section>


<!-- RECEIPT -->

<section id="receipt" class="section">

<div class="title">

    <h2>فیش حضور</h2>

    <p>
        آخرین فیش صادرشده
    </p>

</div>

<div id="receiptSection" class="receipt-box">

<div class="empty">
    هنوز فیشی صادر نشده است.
</div>

</div>

</section>

</main>


<div id="toast" class="toast"></div>


<script>

/* =========================
   SETTINGS
========================= */

const CAPACITY = 100;

const DAYS = [
    {id:"27", title:"۲۷ آبان"},
    {id:"28", title:"۲۸ آبان"},
    {id:"29", title:"۲۹ آبان"},
    {id:"30", title:"۳۰ آبان"},
    {id:"31", title:"۳۱ آبان"}
];

const STORAGE_KEY = "attendance_records_v1";


/* =========================
   DATA
========================= */

let records =
    JSON.parse(localStorage.getItem(STORAGE_KEY)) || [];

let womenCount = 0;
let menCount = 0;


/* =========================
   SAVE
========================= */

function saveData(){

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(records)
    );

}


/* =========================
   NAVIGATION
========================= */

function showSection(id, button){

    document
        .querySelectorAll(".section")
        .forEach(section=>{
            section.classList.remove("active");
        });

    document
        .getElementById(id)
        .classList.add("active");

    document
        .querySelectorAll(".nav button")
        .forEach(btn=>{
            btn.classList.remove("active");
        });

    if(button){
        button.classList.add("active");
    }

    if(id==="dashboard"){
        renderDashboard();
    }

    if(id==="records"){
        renderRecords();
    }

}


/* =========================
   COUNTER
========================= */

function changeCount(type, amount){

    if(type==="women"){

        womenCount += amount;

        if(womenCount < 0){
            womenCount = 0;
        }

        if(womenCount > 100){
            womenCount = 100;
        }

        document.getElementById("women").textContent =
            womenCount;
    }


    if(type==="men"){

        menCount += amount;

        if(menCount < 0){
            menCount = 0;
        }

        if(menCount > 100){
            menCount = 100;
        }

        document.getElementById("men").textContent =
            menCount;
    }

}


/* =========================
   REGISTER
========================= */

function registerPerson(){

    const name =
        document.getElementById("name").value.trim();

    const phone =
        document.getElementById("phone").value.trim();

    const day =
        document.getElementById("day").value;


    if(!name){

        toast("نام و نام خانوادگی را وارد کنید.");

        return;
    }


    if(!phone){

        toast("شماره همراه را وارد کنید.");

        return;
    }


    if(!/^09\d{9}$/.test(phone)){

        toast("شماره همراه معتبر نیست.");

        return;
    }


    if(!day){

        toast("روز حضور را انتخاب کنید.");

        return;
    }


    const total = womenCount + menCount;


    if(total <= 0){

        toast("حداقل یک نفر باید ثبت شود.");

        return;
    }


    const already =
        getDayTotal(day);


    if(already + total > CAPACITY){

        const remaining =
            CAPACITY - already;

        toast(
            "ظرفیت این روز فقط " +
            remaining +
            " نفر باقی مانده است."
        );

        return;
    }


    const record = {

        id:
            Date.now() +
            "-" +
            Math.floor(Math.random()*999),

        tracking:
            createTrackingCode(),

        name:name,

        phone:phone,

        women:womenCount,

        men:menCount,

        total:total,

        day:day,

        createdAt:
            new Date().toLocaleString("fa-IR")

    };


    records.push(record);

    saveData();


    document.getElementById("name").value="";
    document.getElementById("phone").value="";
    document.getElementById("day").value="";

    womenCount=0;
    menCount=0;

    document.getElementById("women").textContent="0";
    document.getElementById("men").textContent="0";


    showReceipt(record);

    toast("ثبت با موفقیت انجام شد.");

}


/* =========================
   TRACKING CODE
========================= */

function createTrackingCode(){

    const random =
        Math.floor(100000 + Math.random()*900000);

    return "H-" + random;

}


/* =========================
   DAY TOTAL
========================= */

function getDayTotal(day){

    return records
        .filter(record=>record.day===day)
        .reduce(
            (sum,record)=>sum+record.total,
            0
        );

}


/* =========================
   DASHBOARD
========================= */

function renderDashboard(){

    let totalPeople=0;
    let totalWomen=0;
    let totalMen=0;


    records.forEach(record=>{

        totalPeople += record.total;
        totalWomen += record.women;
        totalMen += record.men;

    });


    document.getElementById("totalPeople")
        .textContent=totalPeople;

    document.getElementById("totalWomen")
        .textContent=totalWomen;

    document.getElementById("totalMen")
        .textContent=totalMen;

    document.getElementById("totalRecords")
        .textContent=records.length;


    const container =
        document.getElementById("daysContainer");


    container.innerHTML="";


    DAYS.forEach(day=>{

        const total =
            getDayTotal(day.id);

        const percent =
            Math.min(
                100,
                Math.round(
                    total/CAPACITY*100
                )
            );


        const remaining =
            Math.max(
                0,
                CAPACITY-total
            );


        container.innerHTML += `

            <div class="day">

                <h3>${day.title}</h3>

                <div class="day-number">
                    ${total}
                </div>

                <small>
                    نفر ثبت شده
                </small>

                <div class="progress">
                    <div style="width:${percent}%"></div>
                </div>

                <div class="full-text">

                    ${percent}% ظرفیت پر شده

                    <br>

                    ${remaining} نفر ظرفیت باقی‌مانده

                </div>

            </div>

        `;

    });

}


/* =========================
   RECORDS
========================= */

function renderRecords(){

    const container =
        document.getElementById("recordsContainer");

    const search =
        document.getElementById("search")
        .value
        .trim()
        .toLowerCase();


    let filtered = records.filter(record=>{

        return (

            record.name.toLowerCase().includes(search)

            ||

            record.phone.includes(search)

            ||

            record.tracking
                .toLowerCase()
                .includes(search)

        );

    });


    filtered =
        [...filtered].reverse();


    if(filtered.length===0){

        container.innerHTML=`

            <div class="empty">

                هنوز ثبت اطلاعاتی انجام نشده است.

            </div>

        `;

        return;
    }


    container.innerHTML="";


    filtered.forEach(record=>{

        const day =
            DAYS.find(d=>d.id===record.day);


        container.innerHTML += `

            <div class="record">

                <div class="record-info">

                    <h3>
                        ${escapeHTML(record.name)}
                    </h3>

                    <p>

                        📱 ${escapeHTML(record.phone)}

                        <br>

                        📅 ${day ? day.title : "-"}

                        <br>

                        👩 ${record.women}
                        &nbsp;&nbsp;
                        👨 ${record.men}

                        &nbsp;&nbsp;
                        👥 ${record.total}

                        <br>

                        🎫 ${record.tracking}

                    </p>

                </div>

                <div class="record-actions">

                    <button
                        class="small-btn"
                        onclick="openRecord('${record.id}')"
                    >
                        فیش
                    </button>

                    <button
                        class="small-btn delete"
                        onclick="deleteRecord('${record.id}')"
                    >
                        حذف
                    </button>

                </div>

            </div>

        `;

    });

}


/* =========================
   OPEN RECORD
========================= */

function openRecord(id){

    const record =
        records.find(r=>r.id===id);

    if(!record){
        return;
    }

    showReceipt(record);

    document
        .querySelectorAll(".nav button")
        .forEach(btn=>btn.classList.remove("active"));

}


/* =========================
   RECEIPT
========================= */

function showReceipt(record){

    const day =
        DAYS.find(d=>d.id===record.day);


    const container =
        document.getElementById("receiptSection");


    container.innerHTML=`

        <div class="receipt">

            <div class="receipt-top">

                <div class="receipt-icon">
                    🎫
                </div>

                <h2>
                    فیش ثبت حضور
                </h2>

                <p>
                    ثبت با موفقیت انجام شد
                </p>

            </div>


            <div class="receipt-body">

                <div class="receipt-row">

                    <span>
                        نام و نام خانوادگی
                    </span>

                    <span>
                        ${escapeHTML(record.name)}
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        شماره همراه
                    </span>

                    <span>
                        ${escapeHTML(record.phone)}
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        روز حضور
                    </span>

                    <span>
                        ${day ? day.title : "-"}
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        تعداد خانم
                    </span>

                    <span>
                        ${record.women} نفر
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        تعداد آقا
                    </span>

                    <span>
                        ${record.men} نفر
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        مجموع افراد
                    </span>

                    <span>
                        ${record.total} نفر
                    </span>

                </div>


                <div class="receipt-row">

                    <span>
                        زمان ثبت
                    </span>

                    <span>
                        ${record.createdAt}
                    </span>

                </div>


                <div class="tracking">

                    <small>
                        کد پیگیری
                    </small>

                    <strong>
                        ${record.tracking}
                    </strong>

                </div>

            </div>

        </div>


        <div class="receipt-actions">

            <button onclick="downloadReceipt('${record.id}')">
                ⬇ دانلود فیش
            </button>

            <button onclick="printReceipt()">
                🖨 چاپ / ذخیره PDF
            </button>

        </div>

    `;


    showSection("receipt",null);

}


/* =========================
   DOWNLOAD RECEIPT
========================= */

function downloadReceipt(id){

    const record =
        records.find(r=>r.id===id);

    if(!record){
        return;
    }


    const day =
        DAYS.find(d=>d.id===record.day);


    const html = `

<!DOCTYPE html>

<html lang="fa" dir="rtl">

<head>

<meta charset="UTF-8">

<title>فیش ${record.tracking}</title>

<style>

body{
    font-family:Tahoma;
    background:#f3f3f3;
    padding:30px;
}

.box{
    max-width:500px;
    margin:auto;
    background:white;
    padding:30px;
    border-radius:15px;
    box-shadow:0 10px 30px #ccc;
}

h1{
    text-align:center;
}

.row{
    display:flex;
    justify-content:space-between;
    padding:13px 0;
    border-bottom:1px solid #ddd;
}

.code{
    text-align:center;
    margin-top:25px;
    padding:15px;
    border:1px dashed #555;
}

</style>

</head>

<body>

<div class="box">

<h1>فیش ثبت حضور</h1>

<div class="row">
<span>نام</span>
<strong>${escapeHTML(record.name)}</strong>
</div>

<div class="row">
<span>شماره</span>
<strong>${escapeHTML(record.phone)}</strong>
</div>

<div class="row">
<span>روز حضور</span>
<strong>${day ? day.title : "-"}</strong>
</div>

<div class="row">
<span>خانم</span>
<strong>${record.women} نفر</strong>
</div>

<div class="row">
<span>آقا</span>
<strong>${record.men} نفر</strong>
</div>

<div class="row">
<span>مجموع</span>
<strong>${record.total} نفر</strong>
</div>

<div class="code">

کد پیگیری

<h2>${record.tracking}</h2>

</div>

</div>

</body>

</html>

`;


    const blob =
        new Blob(
            [html],
            {type:"text/html;charset=utf-8"}
        );


    const url =
        URL.createObjectURL(blob);


    const a =
        document.createElement("a");

    a.href=url;

    a.download =
        "fish-" +
        record.tracking +
        ".html";

    a.click();


    URL.revokeObjectURL(url);

}


/* =========================
   PRINT
========================= */

function printReceipt(){

    window.print();

}


/* =========================
   DELETE
========================= */

function deleteRecord(id){

    const record =
        records.find(r=>r.id===id);


    if(!record){
        return;
    }


    const ok =
        confirm(
            "آیا از حذف این ثبت مطمئن هستید؟"
        );


    if(!ok){
        return;
    }


    records =
        records.filter(r=>r.id!==id);


    saveData();

    renderRecords();

    renderDashboard();

    toast("ثبت حذف شد.");

}


/* =========================
   RESET ALL
========================= */

function resetAll(){

    const password =
        prompt(
            "برای ریست کامل اطلاعات، رمز را وارد کنید:"
        );


    if(password===null){
        return;
    }


    if(password!=="1234"){

        toast("رمز اشتباه است.");

        return;
    }


    const confirmReset =
        confirm(
            "هشدار!\n\nتمام ثبت‌ها و آمار برای همیشه پاک می‌شوند.\n\nادامه می‌دهید؟"
        );


    if(!confirmReset){
        return;
    }


    records=[];

    localStorage.removeItem(STORAGE_KEY);


    renderRecords();

    renderDashboard();


    document.getElementById("receiptSection").innerHTML=`

        <div class="empty">
            اطلاعات با موفقیت ریست شد.
        </div>

    `;


    toast("تمام اطلاعات پاک شد.");

}


/* =========================
   TOAST
========================= */

let toastTimer;


function toast(message){

    const element =
        document.getElementById("toast");


    element.textContent=message;

    element.classList.add("show");


    clearTimeout(toastTimer);


    toastTimer =
        setTimeout(()=>{

            element.classList.remove("show");

        },3000);

}


/* =========================
   SECURITY / HTML ESCAPE
========================= */

function escapeHTML(text){

    return String(text)
        .replace(/&/g,"&amp;")
        .replace(/</g,"&lt;")
        .replace(/>/g,"&gt;")
        .replace(/"/g,"&quot;")
        .replace(/'/g,"&#039;");

}


/* =========================
   INITIALIZE
========================= */

renderDashboard();

renderRecords();

</script>

</body>
</html>
