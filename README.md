<!DOCTYPE html>
<html lang="fa">

<head>
    <meta charset="UTF-8">
    <title>PixelMehrshad</title>
    <style>
        body {
            font-family: Tahoma;
            margin: 0;
            color: #fff;
            background: #1a1a1a;
            /* بک‌گراند یکدست */
            overflow-x: hidden;
        }

        header {
            background: rgba(0, 0, 0, 0.85);
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
            position: relative;
        }

        .logo {
            font-size: 1.8em;
            font-weight: bold;
        }

        .hamburger {
            cursor: pointer;
            width: 25px;
            height: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .hamburger div {
            height: 3px;
            background: #fff;
            border-radius: 2px;
        }

        /* منوی کوچک افقی */
        .menu-bar {
            display: none;
            position: absolute;
            top: 60px;
            right: 20px;
            background: rgba(30, 30, 30, 0.95);
            padding: 6px 10px;
            border-radius: 8px;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.6);
            flex-direction: row;
            gap: 10px;
        }

        .menu-bar a {
            color: #fff;
            text-decoration: none;
            font-size: 0.85em;
        }

        .menu-bar a:hover {
            color: #4CAF50;
        }

        section {
            padding: 60px 20px;
            text-align: center;
            background: rgba(20, 20, 20, 0.85);
            margin: 40px auto;
            max-width: 900px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.7);
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #4CAF50;
            margin-bottom: 20px;
        }

        .card {
            background: rgba(40, 40, 40, 0.9);
            color: #fff;
            padding: 20px;
            margin: 15px auto;
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.6);
            max-width: 400px;
        }

        textarea {
            width: 80%;
            padding: 10px;
            border-radius: 5px;
            border: none;
            resize: none;
            background: #222;
            color: #fff;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: #4CAF50;
            color: #fff;
            cursor: pointer;
            margin-top: 10px;
            transition: 0.3s;
        }

        button:hover {
            background-color: #45a049;
            transform: scale(1.05);
        }

        footer {
            background: rgba(0, 0, 0, 0.85);
            color: #fff;
            text-align: center;
            padding: 10px;
            margin-top: 40px;
            box-shadow: 0 -2px 8px rgba(0, 0, 0, 0.5);
        }

        #projectMessage {
            font-weight: bold;
        }
    </style>
</head>

<body>
    <header>
        <div class="logo">PixelMehrshad</div>
        <div class="hamburger" id="hamburger">
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="menu-bar" id="menuBar">
            <a href="#about">درباره من</a>
            <a href="#projects">پروژه‌ها</a>
        </div>
    </header>

    <section id="about">
        <img src="URL_پروفایل" alt="پروفایل مهرشاد" class="profile-img">
        <h2>درباره من</h2>
        <p>سلام! من مهرشاد، کدنویس و عاشق خلق چیزای جالب در وب. خوشحالم که اینجا هستی!</p>
    </section>

    <section id="projects">
        <h2>نمونه‌کارها</h2>
        <div class="card">پروژه ۱</div>
        <div class="card">پروژه ۲</div>
        <div class="card">پروژه ۳</div>

        <h3>ثبت پروژه خودت</h3>
        <form id="projectForm">
            <textarea id="projectInput" rows="4" placeholder="اینجا پروژه خودتو بنویس..."></textarea><br>
            <button type="submit">ارسال پروژه</button>
        </form>
        <p id="projectMessage"></p>
    </section>

    <section id="contact">
        <h2>تماس با من</h2>
        <p>ایمیل: <a href="mailto:mehrshadaslani79@gmail.com" style="color:#4CAF50;">mehrshadaslani79@gmail.com</a></p>
        <p>اینستاگرام: <a href="https://www.instagram.com/mrshwd_a79" target="_blank"
                style="color:#4CAF50;">@mrshwd_a79</a></p>
    </section>

    <footer>
        <p>© 2025 PixelMehrshad</p>
    </footer>

    <script>
        // همبرگر منو باز/بسته
        const hamburger = document.getElementById('hamburger');
        const menuBar = document.getElementById('menuBar');
        hamburger.addEventListener('click', () => {
            if (menuBar.style.display === "flex") {
                menuBar.style.display = "none";
            } else {
                menuBar.style.display = "flex";
            }
        });

        // فرم ثبت پروژه با شرط مخفی و هدایت به پرداخت آنلاین
        const form = document.getElementById('projectForm');
        const input = document.getElementById('projectInput');
        const message = document.getElementById('projectMessage');

        form.addEventListener('submit', function (e) {
            e.preventDefault();
            const text = input.value.trim();
            if (text.includes('پروژه')) {
                message.style.color = 'lightgreen';
                message.textContent = "پروژه شما با موفقیت ثبت شد! در حال انتقال به پرداخت...";
                input.value = '';
                setTimeout(() => {
                    window.location.href = "URL_پرداخت";
                }, 1500);
            } else {
                input.value = '';
                message.textContent = "";
            }
        });
    </script>
</body>

</html>
