
```html name="index.html"
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>سایت علوم هشتم - یادگیری آسان و تعاملی</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #7cf3ff;
            --secondary: #00d47a;
            --dark: #050814;
            --darker: #0a0e1a;
            --text: #d7e2ff;
            --text-light: #aee9ff;
            --bg-light: rgba(79, 141, 255, 0.15);
            --border: rgba(124, 243, 255, 0.3);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #050814 0%, #1a1a3f 100%);
            color: var(--text);
            direction: rtl;
            min-height: 100vh;
        }

        /* ==================== ناوبار ==================== */
        .navbar {
            background: rgba(5, 8, 20, 0.95);
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            color: var(--text);
            text-decoration: none;
            transition: 0.3s;
            font-weight: 500;
        }

        .nav-menu a:hover {
            color: var(--primary);
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: var(--primary);
            margin: 5px 0;
            border-radius: 3px;
            transition: 0.3s;
        }

        /* ==================== بخش‌ها ==================== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .section {
            display: none;
            min-height: 100vh;
            padding: 2rem 0;
            animation: fadeIn 0.5s ease-in;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* ==================== صفحه خانه ==================== */
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            padding: 4rem 2rem;
            margin-bottom: 4rem;
        }

        .hero-content h1 {
            font-size: 2.8rem;
            color: var(--primary);
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .hero-content p {
            font-size: 1.2rem;
            color: var(--text-light);
            margin-bottom: 2rem;
            line-height: 1.6;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--dark);
            border: none;
            padding: 1rem 2.5rem;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
            font-size: 1.1rem;
        }

        .btn-primary:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(124, 243, 255, 0.4);
        }

        .floating-cards {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1.5rem;
        }

        .card-item {
            background: rgba(79, 141, 255, 0.2);
            border: 2px solid var(--primary);
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            font-size: 3.5rem;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* آمار */
        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .stat-card {
            background: var(--bg-light);
            border-radius: 12px;
            padding: 2.5rem;
            text-align: center;
            border: 1px solid var(--border);
            transition: 0.3s;
        }

        .stat-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .stat-card h3 {
            color: var(--primary);
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .stat-card p {
            color: var(--text-light);
        }

        /* ==================== فصل‌ها ==================== */
        .page-title {
            font-size: 2.2rem;
            color: var(--primary);
            margin-bottom: 2rem;
            text-align: center;
        }

        .chapters-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .chapter-card {
            background: var(--bg-light);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 2.5rem;
            cursor: pointer;
            transition: all 0.3s;
        }

        .chapter-card:hover {
            transform: translateY(-8px);
            border-color: var(--primary);
            box-shadow: 0 15px 40px rgba(124, 243, 255, 0.2);
        }

        .chapter-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .chapter-card h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .chapter-card p {
            font-size: 0.95rem;
            color: var(--text-light);
        }

        /* ==================== تفاصیل درس ==================== */
        .lesson-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .btn-back {
            background: var(--bg-light);
            color: var(--primary);
            border: 1px solid var(--border);
            padding: 0.8rem 1.5rem;
            border-radius: 6px;
            cursor: pointer;
            transition: 0.3s;
            font-weight: bold;
        }

        .btn-back:hover {
            border-color: var(--primary);
            background: rgba(124, 243, 255, 0.1);
        }

        .lesson-section {
            background: var(--bg-light);
            border-radius: 12px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            border-right: 3px solid var(--primary);
        }

        .lesson-section h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 1.4rem;
        }

        .lesson-section p {
            color: var(--text);
            margin-bottom: 1rem;
            line-height: 1.8;
        }

        .lesson-section ul {
            padding-right: 2rem;
            margin-bottom: 1rem;
        }

        .lesson-section li {
            margin-bottom: 0.8rem;
            color: var(--text);
            line-height: 1.6;
        }

        /* ==================== آزمون ==================== */
        .exam-start {
            background: var(--bg-light);
            border-radius: 12px;
            padding: 4rem;
            text-align: center;
            border: 1px solid var(--border);
            max-width: 600px;
            margin: 3rem auto;
        }

        .exam-start h3 {
            color: var(--primary);
            font-size: 1.8rem;
            margin-bottom: 2rem;
        }

        .exam-info {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .exam-info-item {
            background: rgba(124, 243, 255, 0.1);
            padding: 1.5rem;
            border-radius: 8px;
            border: 1px solid var(--border);
        }

        .exam-info-item h4 {
            color: var(--primary);
            margin-bottom: 0.5rem;
        }

        .exam-info-item p {
            color: var(--text-light);
        }

        .progress-bar {
            width: 100%;
            height: 10px;
            background: rgba(79, 141, 255, 0.1);
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 2rem;
        }

        .progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            width: 0%;
            transition: width 0.3s;
        }

        .question-card {
            background: var(--bg-light);
            border-radius: 12px;
            padding: 3rem;
            margin-bottom: 2rem;
            border: 1px solid var(--border);
        }

        .question-card h2 {
            color: var(--primary);
            margin-bottom: 2rem;
            font-size: 1.5rem;
        }

        .question-info {
            color: var(--text-light);
            margin-bottom: 2rem;
            font-size: 0.95rem;
        }

        .options {
            display: grid;
            gap: 1.2rem;
            margin-bottom: 2rem;
        }

        .option {
            background: rgba(5, 8, 20, 0.8);
            border: 2px solid var(--border);
            padding: 1.2rem;
            border-radius: 8px;
            cursor: pointer;
            color: var(--text);
            transition: all 0.3s;
        }

        .option:hover {
            border-color: var(--primary);
            background: rgba(79, 141, 255, 0.2);
        }

        .option.selected {
            border-color: var(--primary);
            background: rgba(124, 243, 255, 0.2);
        }

        .option.correct {
            border-color: var(--secondary);
            background: rgba(0, 180, 120, 0.2);
        }

        .option.incorrect {
            border-color: #ff8070;
            background: rgba(220, 100, 80, 0.2);
        }

        .exam-buttons {
            display: flex;
            gap: 1rem;
            justify-content: space-between;
            margin-top: 2rem;
        }

        .results {
            background: rgba(0, 180, 120, 0.1);
            border: 2px solid var(--secondary);
            border-radius: 12px;
            padding: 4rem;
            text-align: center;
            max-width: 600px;
            margin: 3rem auto;
        }

        .results h2 {
            color: var(--secondary);
            font-size: 2rem;
            margin-bottom: 2rem;
        }

        .result-item {
            margin-bottom: 2rem;
        }

        .result-item h3 {
            color: var(--text-light);
            font-size: 1.2rem;
        }

        .result-item p {
            color: var(--primary);
            font-size: 2rem;
            font-weight: bold;
            margin-top: 0.5rem;
        }

        /* ==================== فلش‌کارت ==================== */
        .flashcard-controls {
            margin-bottom: 2rem;
        }

        .flashcard-controls select {
            width: 100%;
            max-width: 400px;
            padding: 1rem;
            background: var(--bg-light);
            border: 1px solid var(--border);
            border-radius: 6px;
            color: var(--text);
            font-size: 1rem;
        }

        .flashcard-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .flashcard {
            background: var(--bg-light);
            border: 2px solid var(--border);
            border-radius: 12px;
            padding: 2.5rem;
            min-height: 300px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
            perspective: 1000px;
        }

        .flashcard:hover {
            transform: scale(1.05);
            border-color: var(--primary);
            box-shadow: 0 15px 40px rgba(124, 243, 255, 0.2);
        }

        .flashcard-inner {
            text-align: center;
            width: 100%;
        }

        .flashcard-front {
            color: var(--primary);
            font-size: 1.1rem;
            font-weight: bold;
        }

        .flashcard-back {
            color: var(--text);
            font-size: 1rem;
            display: none;
        }

        .flashcard.flipped .flashcard-front {
            display: none;
        }

        .flashcard.flipped .flashcard-back {
            display: block;
        }

        /* ==================== درباره ==================== */
        .about-content {
            background: var(--bg-light);
            border-radius: 12px;
            padding: 3rem;
            border: 1px solid var(--border);
        }

        .about-content h3 {
            color: var(--primary);
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
        }

        .about-content ul {
            margin-top: 1rem;
            padding-right: 2rem;
        }

        .about-content li {
            margin-bottom: 1rem;
            color: var(--text);
            line-height: 1.8;
        }

        /* ==================== فوتر ==================== */
        .footer {
            background: rgba(5, 8, 20, 0.95);
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
            border-top: 1px solid var(--border);
        }

        .footer p {
            color: var(--text-light);
        }

        /* ==================== موبایل ==================== */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }

            .nav-menu {
                display: none;
                position: absolute;
                top: 70px;
                right: 0;
                background: rgba(5, 8, 20, 0.98);
                width: 100%;
                flex-direction: column;
                gap: 1rem;
                padding: 2rem;
                border-bottom: 1px solid var(--border);
            }

            .nav-menu.active {
                display: flex;
            }

            .hero {
                grid-template-columns: 1fr;
                padding: 2rem 1rem;
                gap: 2rem;
            }

            .hero-content h1 {
                font-size: 2rem;
            }

            .chapters-grid {
                grid-template-columns: 1fr;
            }

            .stats-section {
                grid-template-columns: repeat(2, 1fr);
            }

            .lesson-section {
                padding: 1.5rem;
            }

            .exam-info {
                grid-template-columns: 1fr;
            }

            .exam-buttons {
                flex-direction: column;
            }

            .question-card {
                padding: 1.5rem;
            }

            .lesson-header {
                flex-direction: column;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- ==================== ناوبار ==================== -->
    <nav class="navbar">
        <div class="navbar-container">
            <div class="logo">🧪 علوم هشتم</div>
            <ul class="nav-menu" id="navMenu">
                <li><a href="#" onclick="openTab(event, 'home')">🏠 خانه</a></li>
                <li><a href="#" onclick="openTab(event, 'chapters')">📚 درس‌ها</a></li>
                <li><a href="#" onclick="openTab(event, 'exam')">📝 آزمون</a></li>
                <li><a href="#" onclick="openTab(event, 'flashcards')">🧠 فلش‌کارت</a></li>
                <li><a href="#" onclick="openTab(event, 'about')">ℹ️ درباره</a></li>
            </ul>
            <div class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- ==================== صفحه خانه ==================== -->
    <section id="home" class="section active">
        <div class="container">
            <div class="hero">
                <div class="hero-content">
                    <h1>🎓 خوش آمدید به سایت علوم هشتم</h1>
                    <p>یادگیری علوم به روشی ساده، جذاب و تعاملی</p>
                    <p style="font-size: 1rem; color: var(--text-light); margin-top: 1rem;">
                        📚 ۱۰ فصل کامل | 📝 ۵۰ سوال آزمون | 🧠 فلش‌کارت‌های تعاملی
                    </p>
                    <button class="btn-primary" onclick="openTab(event, 'chapters')" style="margin-top: 2rem;">
                        شروع یادگیری
                    </button>
                </div>
                <div class="floating-cards">
                    <div class="card-item">🧬</div>
                    <div class="card-item">⚛️</div>
                    <div class="card-item">🔬</div>
                </div>
            </div>

            <div class="stats-section">
                <div class="stat-card">
                    <h3>10</h3>
                    <p>فصل آموزشی</p>
                </div>
                <div class="stat-card">
                    <h3>50</h3>
                    <p>سوال آزمون</p>
                </div>
                <div class="stat-card">
                    <h3>21</h3>
                    <p>آزمایش عملی</p>
                </div>
                <div class="stat-card">
                    <h3>40+</h3>
                    <p>مفهوم مهم</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== فصل‌ها ==================== -->
    <section id="chapters" class="section">
        <div class="container">
            <h2 class="page-title">📚 درس‌های علوم هشتم</h2>
            <div class="chapters-grid" id="chaptersGrid"></div>
        </div>
    </section>

    <!-- ==================== تفاصیل درس ==================== -->
    <section id="lesson-detail" class="section">
        <div class="container">
            <div class="lesson-header">
                <h2 id="lessonTitle" style="color: var(--primary);">عنوان درس</h2>
                <button class="btn-back" onclick="openTab(event, 'chapters')">← بازگشت</button>
            </div>
            <div id="lessonContent"></div>
        </div>
    </section>

    <!-- ==================== آزمون ==================== -->
    <section id="exam" class="section">
        <div class="container">
            <h2 class="page-title">📝 آزمون جامع علوم هشتم</h2>
            <div id="examContainer">
                <div class="exam-start">
                    <h3>🎯 آزمون فشرده</h3>
                    <div class="exam-info">
                        <div class="exam-info-item">
                            <h4>50</h4>
                            <p>سوال</p>
                        </div>
                        <div class="exam-info-item">
                            <h4>60</h4>
                            <p>دقیقه</p>
                        </div>
                        <div class="exam-info-item">
                            <h4>70%</h4>
                            <p>حد قبول</p>
                        </div>
                    </div>
                    <button class="btn-primary" onclick="startExam()">شروع آزمون</button>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== فلش‌کارت ==================== -->
    <section id="flashcards" class="section">
        <div class="container">
            <h2 class="page-title">🧠 فلش‌کارت‌های مطالعه</h2>
            <div class="flashcard-controls">
                <select id="chapterSelect" onchange="loadFlashcards()">
                    <option value="">انتخاب فصل...</option>
                    <option value="1">فصل ۱: مخلوط و جداسازی</option>
                    <option value="2">فصل ۲: تغییرهای شیمیایی</option>
                    <option value="3">فصل ۳: اتم</option>
                    <option value="4">فصل ۴: تنظیم عصبی</option>
                    <option value="5">فصل ۵: حس و حرکت</option>
                    <option value="6">فصل ۶: تنظیم هورمونی</option>
                    <option value="7">فصل ۷: زیست‌فناوری</option>
                    <option value="8">فصل ۸: تولید مثل</option>
                    <option value="9">فصل ۹: الکتریسیته</option>
                    <option value="10">فصل ۱۰: مغناطیس</option>
                </select>
            </div>
            <div id="flashcardContainer" class="flashcard-container"></div>
        </div>
    </section>

    <!-- ==================== درباره ==================== -->
    <section id="about" class="section">
        <div class="container">
            <h2 class="page-title">ℹ️ درباره این سایت</h2>
            <div class="about-content">
                <h3>سایت علوم هشتم</h3>
                <p>یک منبع آموزشی جامع و تعاملی برای دانش‌آموزان پایه‌ی هشتم</p>
                
                <h3 style="margin-top: 2rem;">🌟 ویژگی‌های سایت</h3>
                <ul>
                    <li>✅ <strong>۱۰ فصل کامل</strong> - تمام مباحث علوم هشتم</li>
                    <li>✅ <strong>توضیحات شفاف</strong> - هر موضوع به صورت تفصیلی</li>
                    <li>✅ <strong>۵۰ سوال آزمون</strong> - برای ارزیابی یادگیری</li>
                    <li>✅ <strong>فلش‌کارت‌های تعاملی</strong> - برای مطالعه سریع</li>
                    <li>✅ <strong>آزمایش‌های عملی</strong> - مثال‌های واقعی</li>
                    <li>✅ <strong>طراحی موبایل‌دوست</strong> - برای تمام دستگاه‌ها</li>
                </ul>

                <h3 style="margin-top: 2rem;">📖 محتویات</h3>
                <ul>
                    <li>فصل ۱: مخلوط و جداسازی مواد</li>
                    <li>فصل ۲: تغییرهای شیمیایی</li>
                    <li>فصل ۳: اتم</li>
                    <li>فصل ۴: تنظیم عصبی</li>
                    <li>فصل ۵: حس و حرکت</li>
                    <li>فصل ۶: تنظیم هورمونی</li>
                    <li>فصل ۷: زیست‌فناوری</li>
                    <li>فصل ۸: تولید مثل</li>
                    <li>فصل ۹: الکتریسیته</li>
                    <li>فصل ۱۰: مغناطیس</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- ==================== فوتر ==================== -->
    <footer class="footer">
        <p>&copy; 2024 سایت علوم هشتم | تمام حقوق محفوظ است | ساخته شده با ❤️</p>
    </footer>

    <script>
        // داده‌های فصل‌ها
        const chapters = [
            {
                id: 1,
                title: "فصل ۱: مخلوط و جداسازی مواد",
                icon: "🧪",
                description: "مخلوط‌ها و روش‌های جداسازی",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 مخلوط چیست؟</h3>
                        <p>مخلوط ترکیب دو یا چند ماده است که می‌توان آن‌ها را جدا کرد.</p>
                        <ul>
                            <li><strong>مخلوط همگن:</strong> جزءهای آن دیده نمی‌شوند (مثل: آب‌نمک)</li>
                            <li><strong>مخلوط ناهمگن:</strong> جزءهای آن به چشم دیده می‌شوند (مثل: شن و آب)</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 روش‌های جداسازی</h3>
                        <ul>
                            <li><strong>الک کردن:</strong> برای جداسازی دانه‌های درشت</li>
                            <li><strong>صاف کردن:</strong> برای جداسازی مایع و جامد</li>
                            <li><strong>تقطیر:</strong> برای جداسازی مایع‌های مختلف</li>
                            <li><strong>تبخیر:</strong> برای جداسازی نمک از آب</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 مثال‌ها</h3>
                        <ul>
                            <li>جداسازی نمک از آب: تبخیر</li>
                            <li>جداسازی شن از آب: صاف کردن</li>
                            <li>جداسازی برنج از سنگ: الک کردن</li>
                            <li>جداسازی آب از الکل: تقطیر</li>
                        </ul>
                    </div>
                `
            },
            {
                id: 2,
                title: "فصل ۲: تغییرهای شیمیایی",
                icon: "⚗️",
                description: "تغییرهای فیزیکی و شیمیایی",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 تغییر فیزیکی</h3>
                        <p>تغییری که ماده‌ی را تغییر نمی‌دهد (فقط شکل یا حالت تغییر می‌کند)</p>
                        <ul>
                            <li>ذوب یخ → آب</li>
                            <li>جوش آب → بخار</li>
                            <li>بریدن کاغذ</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 تغییر شیمیایی</h3>
                        <p>تغییری که ماده‌های جدید ایجاد می‌کند (ترکیب شیمیایی تغییر می‌کند)</p>
                        <ul>
                            <li>سوختن شمع</li>
                            <li>زنگ زدن آهن</li>
                            <li>فاسد شدن غذا</li>
                            <li>درخشندگی قلعی</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 نشانه‌های تغییر شیمیایی</h3>
                        <ul>
                            <li>تغییر رنگ</li>
                            <li>تولید گاز</li>
                            <li>تغییر دما (گرم یا سرد شدن)</li>
                            <li>تشکیل رسوب یا نور</li>
                        </ul>
                    </div>
                `
            },
            {
                id: 3,
                title: "فصل ۳: اتم",
                icon: "⚛️",
                description: "ساختار اتم و اجزاء آن",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 ساختار اتم</h3>
                        <p>اتم از سه ذره اصلی تشکیل شده است:</p>
                        <ul>
                            <li><strong>پروتون:</strong> ذره‌ی مثبت بار در هسته (عدد اتمی)</li>
                            <li><strong>نوترون:</strong> ذره‌ی بدون بار در هسته</li>
                            <li><strong>الکترون:</strong> ذره‌ی منفی بار در اطراف هسته</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 اعداد مهم</h3>
                        <ul>
                            <li><strong>عدد اتمی:</strong> تعداد پروتون‌ها</li>
                            <li><strong>عدد جرمی:</strong> تعداد پروتون + نوترون</li>
                            <li><strong>ایزوتوپ:</strong> اتم‌هایی با عدد اتمی یکسان اما عدد جرمی متفاوت</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 اتم خنثی</h3>
                        <p>در اتم خنثی: تعداد پروتون = تعداد الکترون</p>
                    </div>
                `
            },
            {
                id: 4,
                title: "فصل ۴: تنظیم عصبی",
                icon: "🧠",
                description: "دستگاه عصبی و نقش آن",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 واحد دستگاه عصبی</h3>
                        <p><strong>نورون (سلول عصبی):</strong> سلول‌های عصبی که پیام‌ها را انتقال می‌دهند</p>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 انواع نورون‌ها</h3>
                        <ul>
                            <li><strong>نورون حسی:</strong> محرک را دریافت کرده و به مغز می‌برد</li>
                            <li><strong>نورون رابط:</strong> ارتباط بین نورون‌ها برقرار می‌کند</li>
                            <li><strong>نورون حرکتی:</strong> پیام را از مغز گرفته به عضله می‌برد</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 بازتاب (Reflex)</h3>
                        <p>واکنش سریع و غیرارادی بدن در برابر محرک</p>
                        <ul>
                            <li>دستتان از آتش کشش می‌خورد</li>
                            <li>سوزن را با دست بر می‌دارید</li>
                            <li>پلک دوباره می‌زنید</li>
                        </ul>
                    </div>
                `
            },
            {
                id: 5,
                title: "فصل ۵: حس و حرکت",
                icon: "👁️",
                description: "اندام‌های حسی و حرکت بدن",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 پنج حس</h3>
                        <ul>
                            <li><strong>بینایی:</strong> چشم نور را دریافت می‌کند</li>
                            <li><strong>شنوایی:</strong> گوش صدا را دریافت می‌کند</li>
                            <li><strong>بویایی:</strong> بینی بو را دریافت می‌کند</li>
                            <li><strong>چشایی:</strong> زبان مزه را دریافت می‌کند</li>
                            <li><strong>لامسه:</strong> پوست دما، فشار و درد را دریافت می‌کند</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 حرکت بدن</h3>
                        <p>حرکت نتیجه‌ی همکاری اعصاب و ماهیچه‌ها است:</p>
                        <ul>
                            <li>اعصاب سیگنال می‌فرستند</li>
                            <li>ماهیچه‌ها قرارداد (انقباض) می‌کنند</li>
                            <li>استخوان‌ها حرکت می‌کنند</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 گوش و تعادل</h3>
                        <p>گوش نه‌تنها صدا را شنیدار می‌کند بلکه تعادل بدن را هم حفظ می‌کند.</p>
                    </div>
                `
            },
            {
                id: 6,
                title: "فصل ۶: تنظیم هورمونی",
                icon: "🔬",
                description: "هورمون‌ها و نقش آن‌ها",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 هورمون چیست؟</h3>
                        <p>ماده‌ی شیمیایی که توسط غدد درون‌ریز ترشح شده و وارد خون می‌شود.</p>
                        <p style="margin-top: 1rem;"><strong>اثر هورمون‌ها:</strong> آهسته اما ماندگار</p>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 غدد درون‌ریز</h3>
                        <ul>
                            <li><strong>هیپوفیز:</strong> "فرمانده‌ی غدد" - سایر غدد را کنترل می‌کند</li>
                            <li><strong>تیروئید:</strong> سوخت و ساز بدن را تنظیم می‌کند</li>
                            <li><strong>لوزالمعده:</strong> قند خون را کنترل می‌کند (انسولین)</li>
                            <li><strong>آدرنال:</strong> برای مقابله با استرس (آدرنالین)</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 انسولین</h3>
                        <p>هورمونی که قند خون را کاهش می‌دهد (لوزالمعده ترشح می‌کند)</p>
                    </div>
                `
            },
            {
                id: 7,
                title: "فصل ۷: زیست‌فناوری",
                icon: "🧬",
                description: "استفاده از موجودات زنده برای تولید",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 زیست‌فناوری چیست؟</h3>
                        <p>استفاده از موجودات زنده یا محصولات آن‌ها برای تولید محصولات مفید</p>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 کاربردهای زیست‌فناوری</h3>
                        <ul>
                            <li><strong>پزشکی:</strong> تولید واکسن، انسولین، آنتی‌بیوتیک</li>
                            <li><strong>کشاورزی:</strong> گیاهان اصلاح‌شده</li>
                            <li><strong>غذایی:</strong> تولید ماست، پنیر، نان</li>
                            <li><strong>محیط زیست:</strong> تصفیه فاضلاب، مدیریت زباله</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 موجودات استفاده‌شده</h3>
                        <p>باکتری‌ها: در تقریباً تمام کاربردهای زیست‌فناوری استفاده می‌شوند</p>
                    </div>
                `
            },
            {
                id: 8,
                title: "فصل ۸: تولید مثل",
                icon: "🌱",
                description: "تولید مثل جنسی و غیرجنسی",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 تولید مثل جنسی</h3>
                        <ul>
                            <li>نیاز به دو والد (نر و ماده)</li>
                            <li>ایجاد تنوع ژنتیکی</li>
                            <li>فرزند با والدین متفاوت است</li>
                            <li>مثال: انسان، پرندگان، ماهی‌ها</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 تولید مثل غیرجنسی</h3>
                        <ul>
                            <li>فقط یک والد</li>
                            <li>سریع و اقتصادی</li>
                            <li>فرزند مشابه والد است</li>
                            <li>تنوع ژنتیکی کم</li>
                            <li>مثال: باکتری‌ها، برخی گیاهان</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 روش‌های تولید مثل غیرجنسی</h3>
                        <ul>
                            <li><strong>دوبخشی:</strong> باکتری را به دو قسمت تقسیم (هر 20 دقیقه)</li>
                            <li><strong>جوانه‌زنی:</strong> جوانه از والد جدا می‌شود</li>
                            <li><strong>قلمه‌زدن:</strong> شاخه‌ای از گیاه جدا کرده و کاشته می‌شود</li>
                        </ul>
                    </div>
                `
            },
            {
                id: 9,
                title: "فصل ۹: الکتریسیته",
                icon: "⚡",
                description: "جریان الکتریکی و مدار",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 جریان الکتریکی</h3>
                        <p>حرکت الکترون‌ها در یک رسانا</p>
                        <ul>
                            <li>واحد: آمپر (A)</li>
                            <li>نماد: I</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 مدار الکتریکی</h3>
                        <ul>
                            <li><strong>مدار بسته:</strong> جریان برقرار است (دستگاه کار می‌کند)</li>
                            <li><strong>مدار باز:</strong> جریان برقرار نیست (دستگاه خاموش)</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 قانون اهم</h3>
                        <p style="background: rgba(124, 243, 255, 0.2); padding: 1rem; border-radius: 6px; margin: 1rem 0;">
                            <strong>R = V / I</strong>
                        </p>
                        <ul>
                            <li>R: مقاومت (اهم Ω)</li>
                            <li>V: ولتاژ (ولت V)</li>
                            <li>I: جریان (آمپر A)</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 اتصال سری و موازی</h3>
                        <ul>
                            <li><strong>سری:</strong> جریان یکسان، ولتاژ تقسیم می‌شود</li>
                            <li><strong>موازی:</strong> ولتاژ یکسان، جریان تقسیم می‌شود</li>
                        </ul>
                    </div>
                `
            },
            {
                id: 10,
                title: "فصل ۱۰: مغناطیس",
                icon: "🧲",
                description: "آهن‌ربا و میدان مغناطیسی",
                content: `
                    <div class="lesson-section">
                        <h3>🔹 آهن‌ربا</h3>
                        <p>جسمی که اجسام فلزی را جذب می‌کند و دارای دو قطب است</p>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 قطب‌های مغناطیسی</h3>
                        <ul>
                            <li><strong>قطب شمال (N):</strong> خطوط مغناطیسی از آن خارج می‌شوند</li>
                            <li><strong>قطب جنوب (S):</strong> خطوط مغناطیسی به آن وارد می‌شوند</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 قانون قطب‌ها</h3>
                        <ul>
                            <li><strong>قطب‌های همنام:</strong> دفع می‌شوند (N-N یا S-S)</li>
                            <li><strong>قطب‌های ناهمنام:</strong> جذب می‌شوند (N-S)</li>
                        </ul>
                    </div>
                    <div class="lesson-section">
                        <h3>🔹 الکترومغناطیس</h3>
                        <p>جریان الکتریکی در سیم پیچ میدان مغناطیسی ایجاد می‌کند</p>
                        <ul>
                            <li>قطب‌نما: از میدان مغناطیسی زمین استفاده می‌کند</li>
                            <li>موتور الکتریکی: الکترومغناطیس استفاده می‌کند</li>
                        </ul>
                    </div>
                `
            }
        ];

        // داده‌های آزمون
        const examQuestionsData = [
            { id: 1, chapter: 1, q: "کدام روش برای جداسازی شن و ماسه مناسب است؟", opts: ["تقطیر", "صاف‌کردن", "الک کردن", "تبخیر"], ans: 2 },
            { id: 2, chapter: 1, q: "محلول آب و نمک چه نوع مخلوطی است؟", opts: ["ناهمگن", "همگن", "جامد", "معلق"], ans: 1 },
            { id: 3, chapter: 1, q: "کدام روش برای جداسازی آب و الکل مناسب است؟", opts: ["تقطیر", "الک", "صاف‌کردن", "ته‌نشینی"], ans: 0 },
            { id: 4, chapter: 2, q: "کدام نشانه تغییر شیمیایی است؟", opts: ["ذوب یخ", "زنگ زدن آهن", "بریدن کاغذ", "تبخیر آب"], ans: 1 },
            { id: 5, chapter: 2, q: "قانون پایستگی جرم بیان می‌کند:", opts: ["جرم تغییر می‌کند", "جرم ثابت می‌ماند", "جرم افزایش می‌یابد", "جرم از بین می‌رود"], ans: 1 },
            { id: 6, chapter: 3, q: "عدد اتمی نشان‌دهنده چیست؟", opts: ["تعداد نوترون", "تعداد الکترون", "تعداد پروتون", "عدد جرمی"], ans: 2 },
            { id: 7, chapter: 3, q: "کدام ذره بدون بار است؟", opts: ["پروتون", "الکترون", "نوترون", "یون"], ans: 2 },
            { id: 8, chapter: 4, q: "واحد سازنده دستگاه عصبی چیست؟", opts: ["مغز", "نخاع", "نورون", "عضله"], ans: 2 },
            { id: 9, chapter: 4, q: "بازتاب چه نوع پاسخی است؟", opts: ["ارادی", "آهسته", "سریع و غیرارادی", "هورمونی"], ans: 2 },
            { id: 10, chapter: 5, q: "چشم چه چیزی را دریافت می‌کند؟", opts: ["صدا", "نور", "بو", "مزه"], ans: 1 },
            { id: 11, chapter: 5, q: "تعادل توسط کدام عضو حفظ می‌شود؟", opts: ["چشم", "بینی", "گوش", "زبان"], ans: 2 },
            { id: 12, chapter: 6, q: "کدام غده فرمانده غدد دیگر است؟", opts: ["تیروئید", "لوزالمعده", "هیپوفیز", "آدرنال"], ans: 2 },
            { id: 13, chapter: 6, q: "انسولین چه کاری انجام می‌دهد؟", opts: ["افزایش قند خون", "کاهش قند خون", "تنظیم ضربان قلب", "رشد قد"], ans: 1 },
            { id: 14, chapter: 7, q: "زیست‌فناوری یعنی:", opts: ["استفاده از ماشین‌ها", "استفاده از موجودات زنده", "استفاده از انرژی", "استفاده از فلزات"], ans: 1 },
            { id: 15, chapter: 7, q: "کدام مورد کاربرد زیست‌فناوری پزشکی است؟", opts: ["تولید نان", "تولید واکسن", "تصفیه آب", "تولید برق"], ans: 1 },
            { id: 16, chapter: 8, q: "تولید مثل جنسی چند والد دارد؟", opts: ["یک", "دو", "سه", "ندارد"], ans: 1 },
            { id: 17, chapter: 8, q: "تولید مثل غیرجنسی چه مزیتی دارد؟", opts: ["تنوع زیاد", "سریع و کم‌هزینه", "پیچیده", "نیازمند دو والد"], ans: 1 },
            { id: 18, chapter: 8, q: "کدام موجود غیرجنسی تولید مثل می‌کند؟", opts: ["انسان", "پرنده", "باکتری", "ماهی"], ans: 2 },
            { id: 19, chapter: 9, q: "جریان الکتریکی چیست؟", opts: ["حرکت الکترون‌ها", "حرکت نور", "حرکت گرما", "حرکت صوت"], ans: 0 },
            { id: 20, chapter: 9, q: "مدار بسته یعنی:", opts: ["جریان قطع است", "جریان برقرار است", "ولتاژ صفر است", "باتری ندارد"], ans: 1 },
            { id: 21, chapter: 9, q: "قانون اهم چیست؟", opts: ["R = V × I", "R = V / I", "R = I / V", "R = V + I"], ans: 1 },
            { id: 22, chapter: 10, q: "قطب‌های همنام چه کاری انجام می‌دهند؟", opts: ["جذب می‌شوند", "دفع می‌شوند", "بدون تغییر می‌مانند", "ناپدید می‌شوند"], ans: 1 },
            { id: 23, chapter: 10, q: "قطب‌های ناهمنام چه کاری انجام می‌دهند؟", opts: ["جذب می‌شوند", "دفع می‌شوند", "بدون تغییر می‌مانند", "ناپدید می‌شوند"], ans: 0 },
            { id: 24, chapter: 10, q: "الکترومغناطیس چگونه ایجاد می‌شود؟", opts: ["آهن‌ربای دائمی", "جریان الکتریکی در سیم پیچ", "میدان الکتریکی", "حرکت نور"], ans: 1 },
            { id: 25, chapter: 10, q: "قطب‌نما بر اساس چه چیزی کار می‌کند؟", opts: ["الکتریسیته", "مغناطیس زمین", "جاذبه", "نور خورشید"], ans: 1 }
        ];

        // داده‌های فلش‌کارت
        const flashcardsData = {
            1: [
                { q: "مخلوط همگن چیست؟", a: "مخلوطی که جزءهای آن دیده نمی‌شوند (مثل: آب‌نمک)" },
                { q: "روش الک کردن برای چه کار می‌رود؟", a: "جداسازی دانه‌های درشت" }
            ],
            2: [
                { q: "تغییر فیزیکی چیست؟", a: "تغییری که ترکیب شیمیایی ماده را تغییر نمی‌دهد" },
                { q: "تغییر شیمیایی چیست؟", a: "تغییری که ترکیب شیمیایی ماده را تغییر می‌دهد" }
            ],
            3: [
                { q: "اتم چیست؟", a: "واحد بنیادی مواد که از هسته و الکترون‌ها تشکیل شده" },
                { q: "پروتون چیست؟", a: "ذره‌ی مثبت بار در هسته اتم" }
            ],
            4: [
                { q: "نورون چیست؟", a: "سلول‌های عصبی که پیام‌ها را انتقال می‌دهند" },
                { q: "بازتاب چه نوع پاسخی است؟", a: "واکنش سریع و غیرارادی بدن در برابر محرک" }
            ],
            5: [
                { q: "چشم چه کار می‌کند؟", a: "نور را دریافت می‌کند و تصویر آن را بوجود می‌آورد" },
                { q: "گوش چه کار می‌کند؟", a: "صدا را دریافت می‌کند و تعادل بدن را حفظ می‌کند" }
            ],
            6: [
                { q: "هورمون چیست؟", a: "ماده‌ی شیمیایی ترشح‌شده توسط غدد درون‌ریز" },
                { q: "هیپوفیز چه نقشی دارد؟", a: "کنترل کردن سایر غدد درون‌ریز" }
            ],
            7: [
                { q: "زیست‌فناوری چیست؟", a: "استفاده از موجودات زنده برای تولید محصولات مفید" },
                { q: "مثال زیست‌فناوری پزشکی چی# hamrah
