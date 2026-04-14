[index.html](https://github.com/user-attachments/files/26717338/index.html)
# Give-me-babe
1<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>可以当我的宝宝吗？</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: "Microsoft YaHei", sans-serif;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .wrapper {
            text-align: center;
            background: white;
            padding: 40px 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }

        #showImage {
            width: 200px;
            height: 200px;
            margin-bottom: 20px;
            object-fit: contain; /* 适配猫咪图片，不拉伸变形 */
            border-radius: 10px;
        }

        .text {
            font-size: 24px;
            color: #333;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        button {
            padding: 12px 30px;
            font-size: 18px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yes {
            background-color: #ff6b6b;
            color: white;
        }

        #yes:hover {
            background-color: #ff4757;
            transform: scale(1.05);
        }

        #no {
            background-color: #ccc;
            color: #333;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <!-- 默认显示你提供的猫咪图片 -->
        <img id="showImage" src="https://p3-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/82ccf3fa144143fdbcf64c7c38958445.png~tplv-a9rns2rl98-24:720:720.png?lk3s=8e244e95&rcl=20260414183542BFE95E0F74CCDDC70F7F&rrcfp=8a172a1a&x-expires=1776767742&x-signature=dJ%2BGvK6p1VUxdlb56tpXIPjfQis%3D" alt="猫咪询问">
        <p id="question" class="text">可以当我的宝宝吗？</p>
        <div class="buttons">
            <button id="yes">可以</button>
            <button id="no">不可以</button>
        </div>
    </div>

    <script>
        const yesBtn = document.getElementById('yes');
        const noBtn = document.getElementById('no');
        const question = document.getElementById('question');
        const showImage = document.getElementById('showImage');
        // 你的猫咪图片基础链接（复用同款风格）
        const catBaseUrl = "https://p3-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/82ccf3fa144143fdbcf64c7c38958445.png~tplv-a9rns2rl98-24:720:720.png?lk3s=8e244e95&rcl=20260414183542BFE95E0F74CCDDC70F7F&rrcfp=8a172a1a&x-expires=1776767742&x-signature=dJ%2BGvK6p1VUxdlb56tpXIPjfQis%3D";

        // 点击“可以”的效果
        yesBtn.addEventListener('click', function () {
            question.textContent = '太好了！';
            showImage.src = catBaseUrl; // 保持猫咪图片（也可替换成开心版猫咪）
            yesBtn.style.display = 'none';
            noBtn.style.display = 'none';
        });

        // 手机 + 电脑 通用：一碰“不可以”就乱跑
        function moveButton() {
            const x = Math.random() * (window.innerWidth - 120);
            const y = Math.random() * (window.innerHeight - 60);
            noBtn.style.position = 'fixed';
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        // 电脑端：鼠标悬浮就跑
        noBtn.addEventListener('mouseover', moveButton);
        // 手机端：触摸就跑
        noBtn.addEventListener('touchstart', function(e){
            e.preventDefault(); // 禁止默认点击行为
            moveButton();
        });

        // 点到“不可以”的效果
        noBtn.addEventListener('click', function () {
            question.textContent = '再考虑一下嘛~';
            showImage.src = catBaseUrl; // 保持猫咪图片（也可替换成委屈版猫咪）
        });
    </script>
</body>
</html>
