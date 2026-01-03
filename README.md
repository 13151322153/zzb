<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ZZB · 链上大话 情定万年</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", sans-serif;
        }
        body {
            background-color: #0a0a12;
            color: #fff;
            /* 替换为大话西游主题图片外链 */
            background-image: url("https://p26-sign.douyinpic.com/tos-cn-i-0813c000-ce/o8s7pAfPnTIAeq9BAdwJElFEw1AHApOxD4EqCG~tplv-dy-resize-walign-adapt-aq:720:q75.jpeg?lk3s=138a59ce&x-expires=1768647600&x-signature=a3BfBsoAJATVmA%2FfHivvUO227oo%3D&from=327834062&s=PackSourceEnum_FEED&se=false&sc=cover&biz_tag=aweme_images&l=20260103192932B063F28F1AE8D9A9C284");
            background-attachment: fixed;
            background-size: cover;
            background-position: center;
        }
        .overlay {
            width: 100%;
            height: 100%;
            background-color: rgba(10, 10, 18, 0.75);
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }
        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        /* 导航栏 */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 25px 0;
            border-bottom: 1px solid #3a2e68;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .logo img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            /* 可选：替换为ZZB logo图 */
            content: url("https://picsum.photos/id/1/40/40");
        }
        .logo-text {
            font-size: 24px;
            font-weight: bold;
            color: #ff7e5f;
        }
        .nav-links {
            display: flex;
            gap: 30px;
        }
        .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s;
        }
        .nav-links a:hover {
            color: #ff7e5f;
        }
        /* 首屏Banner */
        .banner {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 40px 0;
        }
        .banner h1 {
            font-size: 48px;
            margin-bottom: 20px;
            background: linear-gradient(to right, #ff7e5f, #feb47b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }
        .banner p {
            font-size: 20px;
            color: #d0d0d0;
            margin-bottom: 40px;
            max-width: 800px;
        }
        .cta-buttons {
            display: flex;
            gap: 20px;
        }
        .cta-buttons a {
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 18px;
            font-weight: bold;
            transition: transform 0.3s;
        }
        .cta-primary {
            background: linear-gradient(to right, #ff7e5f, #feb47b);
            color: #0a0a12;
        }
        .cta-secondary {
            border: 2px solid #ff7e5f;
            color: #ff7e5f;
        }
        .cta-buttons a:hover {
            transform: scale(1.05);
        }
        /* 核心叙事板块 */
        .story {
            padding: 80px 0;
        }
        .story h2 {
            font-size: 36px;
            text-align: center;
            margin-bottom: 40px;
            color: #ff7e5f;
        }
        .story-content {
            font-size: 18px;
            line-height: 1.8;
            color: #e0e0e0;
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
        }
        /* 共识板块 */
        .consensus {
            padding: 60px 0;
            background-color: rgba(18, 18, 30, 0.6);
            border-radius: 10px;
            margin-bottom: 80px;
        }
        .consensus h2 {
            font-size: 36px;
            text-align: center;
            margin-bottom: 40px;
            color: #ff7e5f;
        }
        .consensus-cards {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }
        .card {
            padding: 30px;
            background-color: rgba(30, 25, 50, 0.8);
            border-radius: 8px;
            text-align: center;
        }
        .card h3 {
            font-size: 24px;
            margin-bottom: 20px;
            color: #feb47b;
        }
        .card p {
            color: #d0d0d0;
            line-height: 1.6;
        }
        /* 生态规划 */
        .ecology {
            padding: 80px 0;
        }
        .ecology h2 {
            font-size: 36px;
            text-align: center;
            margin-bottom: 40px;
            color: #ff7e5f;
        }
        .ecology-steps {
            display: flex;
            flex-direction: column;
            gap: 30px;
            max-width: 800px;
            margin: 0 auto;
        }
        .step {
            padding: 25px;
            background-color: rgba(30, 25, 50, 0.8);
            border-left: 4px solid #ff7e5f;
            border-radius: 0 8px 8px 0;
        }
        .step h3 {
            font-size: 22px;
            margin-bottom: 15px;
            color: #feb47b;
        }
        .step p {
            color: #d0d0d0;
            line-height: 1.6;
        }
        /* 社区板块 */
        .community {
            padding: 80px 0;
            text-align: center;
        }
        .community h2 {
            font-size: 36px;
            margin-bottom: 30px;
            color: #ff7e5f;
        }
        .community p {
            font-size: 18px;
            color: #d0d0d0;
            margin-bottom: 40px;
        }
        .community-icons {
            display: flex;
            justify-content: center;
            gap: 40px;
        }
        .community-icons a {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background-color: rgba(30, 25, 50, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background-color 0.3s;
        }
        .community-icons a:hover {
            background-color: #ff7e5f;
        }
        .community-icons img {
            width: 30px;
            height: 30px;
        }
        /* 底部 */
        footer {
            padding: 40px 0;
            text-align: center;
            border-top: 1px solid #3a2e68;
            margin-top: 80px;
        }
        .disclaimer {
            font-size: 14px;
            color: #999;
            max-width: 900px;
            margin: 0 auto 20px;
            line-height: 1.6;
        }
        .copyright {
            font-size: 14px;
            color: #777;
        }
        /* 响应式 */
        @media (max-width: 768px) {
            .nav-links {
                gap: 15px;
            }
            .banner h1 {
                font-size: 36px;
            }
            .consensus-cards {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="overlay"></div>
    <div class="container">
        <!-- 导航栏 -->
        <nav>
            <div class="logo">
                <img src="" alt="ZZB Logo">
                <div class="logo-text">ZZB</div>
            </div>
            <div class="nav-links">
                <a href="#home">首页</a>
                <a href="#story">项目叙事</a>
                <a href="#consensus">生态共识</a>
                <a href="#ecology">生态规划</a>
                <a href="#community">社区</a>
                <a href="#disclaimer">免责声明</a>
            </div>
        </nav>

        <!-- 首屏Banner -->
        <section class="banner" id="home">
            <h1>戴上金箍 护你周全；持有ZZB 共赴纪元</h1>
            <p>以大话西游宿命爱恋为锚，铸区块链情怀共识之币，让爱你一万年成为链上永恒</p>
            <div class="cta-buttons">
                <a href="#story" class="cta-primary">了解叙事</a>
                <a href="#community" class="cta-secondary">加入社区</a>
            </div>
        </section>

        <!-- 核心叙事 -->
        <section class="story" id="story">
            <h2>缘起大话 · 币承深情</h2>
            <div class="story-content">
                他曾是斧头帮桀骜不驯的至尊宝，她是手持紫青宝剑、笑靥明媚的紫霞仙子。<br>
                一句“爱你一万年”，道尽世人藏在心底的遗憾与执念；一次金箍加身，是成长的无奈，更是守护的担当。<br>
                ZZB，不是一枚冰冷的代币，是这份跨越银幕的爱恋，在区块链世界的数字信物。<br>
                我们以情怀为共识，让每一位持有者，都成为“大话同路人”。
            </div>
        </section>

        <!-- 共识板块 -->
        <section class="consensus" id="consensus">
            <h2>ZZB共识 · 不止于币</h2>
            <div class="consensus-cards">
                <div class="card">
                    <h3>情怀共识</h3>
                    <p>致敬经典《大话西游》，聚拢亿万大话迷，以共同的青春记忆筑牢社区根基，让情怀成为最坚实的共识。</p>
                </div>
                <div class="card">
                    <h3>生态共识</h3>
                    <p>锚定元宇宙、IP衍生、周边共创三大方向，打造闭环情怀生态，让ZZB的价值与情怀共生共长。</p>
                </div>
                <div class="card">
                    <h3>技术共识</h3>
                    <p>公开透明合约，去中心化发行，永不增发，让“永恒”的承诺照进区块链现实。</p>
                </div>
            </div>
        </section>

        <!-- 生态规划 -->
        <section class="ecology" id="ecology">
            <h2>链上征程 · 共赴万年</h2>
            <div class="ecology-steps">
                <div class="step">
                    <h3>第一阶段：情怀启航</h3>
                    <p>上线社区论坛，发起“我的大话故事”征集，空投限量NFT（至尊宝/紫霞数字藏品），聚拢核心社区用户。</p>
                </div>
                <div class="step">
                    <h3>第二阶段：生态筑基</h3>
                    <p>搭建ZZB元宇宙“水帘洞”，开放虚拟场景社交，上线链上紫青宝剑盲盒，丰富情怀生态的交互形式。</p>
                </div>
                <div class="step">
                    <h3>第三阶段：万象更新</h3>
                    <p>联动大话IP衍生内容创作，推动社区自治，让ZZB成为情怀与价值并存的社区符号，实现“爱你一万年”的链上约定。</p>
                </div>
            </div>
        </section>

        <!-- 社区板块 -->
        <section class="community" id="community">
            <h2>加入我们 · 做自己的盖世英雄</h2>
            <p>这里没有神仙妖怪，只有一群热爱大话的同路人；扫码加入社区，让“爱你一万年”不再是台词</p>
            <div class="community-icons">
                <a href="#"><img src="https://picsum.photos/id/2/30/30" alt="电报"></a>
                <a href="#"><img src="https://picsum.photos/id/3/30/30" alt="Twitter"></a>
                <a href="#"><img src="https://picsum.photos/id/4/30/30" alt="微信"></a>
            </div>
        </section>

        <!-- 底部 -->
        <footer id="disclaimer">
            <div class="disclaimer">
                免责声明：ZZB为社区自发发起的情怀代币项目，不涉及任何金融募资与承诺。加密货币投资存在极高风险，请谨慎评估自身承受能力，理性参与。本项目仅为《大话西游》IP爱好者的情怀创作，不涉及官方商业授权。
            </div>
            <div class="copyright">Copyright © 2025 ZZB社区 版权所有</div>
        </footer>
    </div>
</body>
</html>
