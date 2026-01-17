# my-website2
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<title>আমার পরিচয়</title>

<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
}

.container{
    display:flex;
    flex-direction:column;
    align-items:center;
    padding:60px 0 30px;
}

/* প্রোফাইল ছবি */
.profile-pic{
    width:120px;
    height:120px;
    border-radius:50%;
    border:5px solid white;
    background:url('0R1A1100.jpg') center/cover no-repeat;
    box-shadow:0 10px 25px rgba(0,0,0,0.3);
    margin-bottom:-60px;
    animation: zoomIn 1.2s ease forwards;
    z-index:2;
}

/* কার্ড */
.card{
    background:white;
    width:90%;
    max-width:400px;
    padding:80px 20px 20px;
    border-radius:15px;
    box-shadow:0 10px 25px rgba(0,0,0,0.2);
    text-align:center;
    animation: slideUp 1s ease forwards;
}

/* নিচের কার্ড */
.card.second{
    margin-top:40px;
    animation-delay:0.8s;
}

/* লক্ষ্য কার্ড */
.card.highlight{
    margin-top:40px;
    background:linear-gradient(135deg,#ffecd2,#fcb69f);
    animation-delay:0.3s;
}

/* Favorite Thing */
.card.third{
    margin-top:30px;
    background:linear-gradient(135deg,#c3cfe2,#f5f7fa);
    animation-delay:0.5s;
    padding:30px;
}

.highlight p,
.rahii .tag{
    background:#ffffffaa;
    padding:8px;
    border-radius:10px;
    margin:8px 5px;
    font-weight:bold;
    color:#444;
}

h1, h2{
    color:#764ba2;
}

p{
    margin:6px 0;
    font-size:16px;
}

.tag{
    display:inline-block;
    background:#667eea;
    color:white;
    padding:6px 14px;
    border-radius:20px;
}

footer{
    margin-top:12px;
    color:#666;
}

button{
    margin-top:15px;
    padding:10px 20px;
    border:none;
    border-radius:25px;
    background:#667eea;
    color:white;
    font-size:15px;
    cursor:pointer;
}

.link-card{
    text-decoration:none;
    color:inherit;
}

/* এনিমেশন */
@keyframes slideUp{
    from{
        transform:translateY(60px);
        opacity:0;
    }
    to{
        transform:translateY(0);
        opacity:1;
    }
}

@keyframes zoomIn{
    from{
        transform:scale(0);
        opacity:0;
    }
    to{
        transform:scale(1);
        opacity:1;
    }
}
</style>
</head>

<body>

<div class="container">

    <!-- 🔵 গোলাকার ছবি -->
    <div class="profile-pic"></div>

    <!-- প্রথম বক্স -->
    <div class="card">
        <h2>স্বাগতম</h2>
        <h1>আমার পরিচয়</h1>
        <p><b>নাম:</b> রাহিনুর রেজা আসিফ</p>
        <p><b>মাদ্রাসা:</b> শাহজালাল জামেয়া ইসলামিয়া কামিল মাদ্রাসা</p>
        <p><b>শ্রেণি:</b> আলিম ১ম বর্ষ</p>
        <p><b>শাখা:</b> A</p>
        <p><b>রোল:</b> ৭৮</p>
        <footer>HSC 27 Batch</footer>
    </div>

    <!-- দ্বিতীয় বক্স -->
    <div class="card highlight">
        <h2>✨ আমার লক্ষ্য</h2>
        <div class="highlight">
            <p>📚 নিয়মিত পড়াশোনা</p>
            <p>💻 ওয়েব ডেভেলপমেন্ট শেখা</p>
            <p>⚽ খেলাধুলা ও ফিটনেস</p>
            <p>🌟 নিজের স্বপ্ন পূরণ</p>
        </div>
    </div>

    <!-- তৃতীয় বক্স -->
    <div class="card third">
        <h2>Favorite Thing</h2>
        <div class="rahii">
            <div class="tag">Lionel Messi</div>
            <div class="tag">Anime</div>
            <div class="tag">Barcelona</div>
            <div class="tag">Sylhet Titans</div>
        </div>
    </div>

    <!-- চতুর্থ বক্স -->
    <div class="card second">
        <a href="second.html" class="link-card">
            <h2>সাথে থাকার জন্য অসংখ্য ধন্যবাদ</h2>
            <p>এটা প্রথম পেইজ</p>
            <p>দ্বিতীয় পেইজে যেতে চাইলে এখানে ক্লিক করুন</p>
        </a>
        <button onclick="goNext()">দ্বিতীয় পেইজে যান →</button>
    </div>

</div>

<script>
function goNext(){
    window.location.href = "second.html";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<title>আমার ফটো গ্যালারি</title>

<style>
body{
    font-family: sans-serif;
    margin:0;
    background:#f5f5f5;
}

/* ===== Gallery ===== */
.gallery{
    display:flex;
    gap:10px;
    flex-wrap:wrap;
    padding:15px;
}

.photo-box{
    border:2px solid #4CAF50;
    padding:12px 18px;
    border-radius:8px;
    background:#f0fff0;
    box-shadow:0 0 8px #aaa;
    cursor:pointer;
    font-weight:bold;
    color:#0066cc;
}

/* ===== Lightbox ===== */
#lightbox{
    display:none;
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,0.8);
    justify-content:center;
    align-items:center;
    z-index:1000;
}

#lightbox img{
    max-width:90%;
    max-height:90%;
    border-radius:10px;
    box-shadow:0 0 20px white;
}

/* ===== Welcome Box ===== */
.welcome-wrapper{
    display:flex;
    justify-content:center;
    margin:40px 0;
}

.welcome-card{
    width:90%;
    max-width:350px;
    background:#ffffff;
    border-radius:18px;
    padding:20px;
    text-align:center;
    box-shadow:0 10px 25px rgba(0,0,0,0.25);
    animation:slideUp 1s ease-out;
}

@keyframes slideUp{
    from{
        transform:translateY(60px);
        opacity:0;
    }
    to{
        transform:translateY(0);
        opacity:1;
    }
}

.welcome-card button{
    margin-top:12px;
    padding:10px 20px;
    border:none;
    border-radius:25px;
    background:#4CAF50;
    color:white;
    font-size:15px;
    cursor:pointer;
}

.welcome-card button:hover{
    background:#43a047;
}

.welcome-wrapper a{
    text-decoration:none;
    color:#333;
}
</style>
</head>

<body>

<h2 style="padding:15px;">📸 আমার ফটো গ্যালারি</h2>

<div class="gallery">
    <div class="photo-box" onclick="openImg('0R1A1057.jpg')">Photo 1</div>
    <div class="photo-box" onclick="openImg('0R1A1100.jpg')">Photo 2</div>
    <div class="photo-box" onclick="openImg('0R1A1102.jpg')">Photo 3</div>
    <div class="photo-box" onclick="openImg('0R1A1087.jpg')">Photo 4</div>
</div>

<!-- Lightbox -->
<div id="lightbox" onclick="closeImg()">
    <img id="bigImg">
</div>

<!-- Welcome Card -->
<div class="welcome-wrapper">
    <a href="third.html">
        <div class="welcome-card"
            <p>এটা ফটো গ্যালারি পেইজ</p>
            <p>পরবর্তী পেইজে যেতে নিচের বাটনে ক্লিক করুন</p>
            <button>পরবর্তী পেইজ →</button>
        </div>
    </a>
</div>

<!-- ===== JavaScript ===== -->
<script>
function openImg(imgName){
    document.getElementById("bigImg").src = imgName;
    document.getElementById("lightbox").style.display = "flex";
}

function closeImg(){
    document.getElementById("lightbox").style.display = "none";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<title>আমার সম্পর্কে ও ধন্যবাদ</title>

<style>
body{
    margin:0;
    font-family: Arial, sans-serif;
    background:#f2f2f2;
    overflow-x:hidden;
}

/* সব সেকশন */
.section{
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
}

/* কার্ড ডিজাইন */
.card{
    background:white;
    width:90%;
    max-width:400px;
    padding:25px;
    border-radius:18px;
    box-shadow:0 12px 30px rgba(0,0,0,0.25);
    text-align:center;
}

/* প্রথম কার্ড এনিমেশন */
.about-card{
    animation: slideFade 1.4s ease forwards;
}

/* ধন্যবাদ সেকশন */
.thankyou-section{
    background: linear-gradient(135deg, #43cea2, #185a9d);
}

/* ধন্যবাদ কার্ড এনিমেশন */
.thank-card{
    animation: zoomFade 1.5s ease forwards;
}

/* টেক্সট এনিমেশন */
.card h1, .card h2, .card h3, .card p{
    animation: textFade 1.2s ease forwards;
}

/* বাটন */
button{
    margin-top:20px;
    background:#4CAF50;
    color:white;
    border:none;
    padding:12px 25px;
    border-radius:30px;
    font-size:16px;
    cursor:pointer;
    transition:transform 0.3s, box-shadow 0.3s;
}

button:hover{
    transform:scale(1.08);
    box-shadow:0 8px 20px rgba(0,0,0,0.3);
}

/* এনিমেশন কিফ্রেম */
@keyframes slideFade{
    from{
        opacity:0;
        transform:translateY(60px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

@keyframes zoomFade{
    from{
        opacity:0;
        transform:scale(0.7);
    }
    to{
        opacity:1;
        transform:scale(1);
    }
}

@keyframes textFade{
    from{
        opacity:0;
    }
    to{
        opacity:1;
    }
}

h1,h2{
    color:#2e7d32;
}

p{
    font-size:16px;
    color:#555;
}
</style>
</head>

<body>

<!-- প্রথম অংশ : আমার সম্পর্কে -->
<div class="section">
    <div class="card about-card">
        <h2>🙋‍♂️ আমার সম্পর্কে</h2>
        <p><b>নাম:</b> আপনার নাম</p>
        <p><b>পেশা:</b> ওয়েবসাইট ডেভেলপার</p>
        <p><b>শখ:</b> কোডিং, ডিজাইন</p>
        <p><b>লক্ষ্য:</b> একজন অধ্যাপক হওয়া</p>

        <hr>

        <h3>📞 যোগাযোগ</h3>
        <p>মোবাইল: 01XXXXXXXXX</p>
        <p>ফেইসবুক: facebook.com/yourid</p>
        <p>ইমেইল: example@gmail.com</p>

        <p style="margin-top:20px;color:#777;">
            ⬇ নিচে স্ক্রল করুন
        </p>
    </div>
</div>

<!-- দ্বিতীয় অংশ : ধন্যবাদ -->
<div class="section thankyou-section">
    <div class="card thank-card">
        <h1>🙏 ধন্যবাদ</h1>
        <p>আমার ওয়েবসাইট ভিজিট করার জন্য আপনাকে অসংখ্য ধন্যবাদ।</p>
        <p>আবার আসবেন 😊</p>

        <button onclick="location.href='নুর2.html'">
            প্রথম পেইজে যান 🔁
        </button>
    </div>
</div>

</body>
</html>
