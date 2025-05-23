```html
<!DOCTYPE html>
<html>
<head>
    <title>恭喜中奖</title>
    <style>
        body {
            background-color: gold;
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: red;
            opacity: 0.7;
        }
    </style>
</head>
<body>
    <h1 style="color:red;font-size:3em;">🎉 恭喜您中奖了！ 🎉</h1>
    <script>
        // 创建彩色纸屑效果
        function createConfetti() {
            for(let i=0; i<100; i++) {
                let confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * window.innerWidth + 'px';
                confetti.style.top = Math.random() * window.innerHeight + 'px';
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 50%)`;
                confetti.style.transform = `rotate(${Math.random() * 360}deg)`;
                document.body.appendChild(confetti);
                
                // 动画效果
                setInterval(() => {
                    confetti.style.top = parseFloat(confetti.style.top) + 5 + 'px';
                    if(parseFloat(confetti.style.top) > window.innerHeight) {
                        confetti.style.top = '0px';
                    }
                }, 100);
            }
        }
        
        window.onload = createConfetti;
    </script>
</body>
</html>
