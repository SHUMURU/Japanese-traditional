# Japanese-t<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>匠心之美 | 日本传统工艺</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@300;500&family=Inter:wght@300;400&display=swap" rel="stylesheet">
</head>
<body>
    <nav class="navbar">
        <div class="container">
            <a href="index.html" class="logo">KOGEI</a>
            <ul class="nav-links">
                <li><a href="index.html" class="active">首页</a></li>
                <li><a href="products.html">工艺品</a></li>
                <li><a href="blog.html">志趣</a></li>
                <li><a href="contact.html">联系</a></li>
            </ul>
        </div>
    </nav>

    <header class="hero">
        <div class="hero-content">
            <h1 class="reveal">静谧之美，源自匠心</h1>
            <p class="reveal">探索跨越千年的日本传统手工艺：陶瓷、漆器与和纸。</p>
            <a href="products.html" class="cta-button reveal">浏览收藏</a>
        </div>
    </header>

    <section class="container">
        <div class="grid">
            <div class="card reveal">
                <div class="card-image"><img src="https://images.unsplash.com/photo-1578749556568-bc2c40e68b61?auto=format&fit=crop&q=80&w=800" alt="陶瓷"></div>
                <div class="card-info"><h3>陶瓷</h3><p>触感细腻的日常美学</p></div>
            </div>
            <!-- 更多卡片可在 GitHub 托管后动态增加 -->
        </div>
    </section>

    <footer class="footer">
        <p>&copy; 2024 Japanese Traditional Crafts. Designed with Minimalist Aesthetics.</p>
    </footer>

    <script src="js/script.js"></script>
</body>
</html>
raditional
:root {
    --primary-color: #1d1d1f;
    --bg-color: #ffffff;
    --accent-color: #8e8e93;
    --text-muted: #6e6e73;
    --transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
    font-family: 'Inter', 'Noto Serif JP', serif;
    background-color: var(--bg-color);
    color: var(--primary-color);
    line-height: 1.6;
}

.container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }

/* 导航栏 */
.navbar {
    position: fixed; top: 0; width: 100%; height: 60px;
    background: rgba(255, 255, 255, 0.8); backdrop-filter: blur(10px);
    z-index: 1000; border-bottom: 1px solid rgba(0,0,0,0.05);
    display: flex; align-items: center;
}

.navbar .container { display: flex; justify-content: space-between; align-items: center; width: 100%; }

.logo { font-size: 1.2rem; font-weight: 500; letter-spacing: 2px; text-decoration: none; color: var(--primary-color); }

.nav-links { display: flex; list-style: none; }

.nav-links li { margin-left: 30px; }

.nav-links a { text-decoration: none; color: var(--primary-color); font-size: 0.9rem; transition: var(--transition); }

.nav-links a.active { color: var(--accent-color); }

/* 入场动画类 */
.reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 1.2s cubic-bezier(0.4, 0, 0.2, 1), transform 1.2s cubic-bezier(0.4, 0, 0.2, 1);
}

.reveal.active { opacity: 1; transform: translateY(0); }

/* 英雄区 */
.hero { height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; background: #fbfbfd; }

.hero-content h1 { font-size: 3.5rem; font-weight: 500; margin-bottom: 20px; }

.cta-button { display: inline-block; padding: 12px 30px; background: var(--primary-color); color: #fff; text-decoration: none; border-radius: 30px; }

/* 页脚 */
.footer { padding: 60px 0; text-align: center; font-size: 0.8rem; color: var(--accent-color); border-top: 1px solid #f2f2f2; }

/* 其他页面的通用 Header */
.page-header { padding: 150px 0 80px; text-align: center; background-color: #fbfbfd; }
document.addEventListener('DOMContentLoaded', () => {
    // 1. 入场动画观察器
    const observerOptions = { threshold: 0.1 };
    const revealObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('active');
            }
        });
    }, observerOptions);

    document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));

    // 2. 导航栏滚动效果
    window.addEventListener('scroll', () => {
        const navbar = document.querySelector('.navbar');
        navbar.style.background = window.scrollY > 50 ? 'rgba(255, 255, 255, 0.95)' : 'rgba(255, 255, 255, 0.8)';
    });
});

