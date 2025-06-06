    
<!DOCTYPE html>    
<html lang="th">    
<head>    
    <meta charset="UTF-8">    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">    
    <title>ลงชื่อเข้าใช้งาน</title>    
    <style>    
        * {    
            margin: 0;    
            padding: 0;    
            box-sizing: border-box;    
        }    
    
        body {    
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;    
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);    
            min-height: 100vh;    
            display: flex;    
            justify-content: center;    
            align-items: center;    
            padding: 20px;    
        }    
    
        .login-container {    
            background: rgba(255, 255, 255, 0.95);    
            padding: 40px;    
            border-radius: 20px;    
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);    
            width: 100%;    
            max-width: 400px;    
            backdrop-filter: blur(10px);    
        }    
    
        .login-header {    
            text-align: center;    
            margin-bottom: 30px;    
        }    
    
        .login-header h1 {    
            color: #333;    
            font-size: 28px;    
            margin-bottom: 10px;    
        }    
    
        .login-header p {    
            color: #666;    
            font-size: 14px;    
        }    
    
        .form-group {    
            margin-bottom: 20px;    
        }    
    
        label {    
            display: block;    
            margin-bottom: 8px;    
            color: #555;    
            font-weight: 500;    
        }    
    
        input[type="text"], input[type="password"] {    
            width: 100%;    
            padding: 15px;    
            border: 2px solid #e1e1e1;    
            border-radius: 10px;    
            font-size: 16px;    
            transition: all 0.3s ease;    
            background: #f9f9f9;    
        }    
    
        input[type="text"]:focus, input[type="password"]:focus {    
            outline: none;    
            border-color: #667eea;    
            background: white;    
            transform: translateY(-2px);    
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.2);    
        }    
    
        .login-btn {    
            width: 100%;    
            padding: 15px;    
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);    
            color: white;    
            border: none;    
            border-radius: 10px;    
            font-size: 16px;    
            font-weight: 600;    
            cursor: pointer;    
            transition: all 0.3s ease;    
            margin-top: 10px;    
        }    
    
        .login-btn:hover {    
            transform: translateY(-2px);    
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);    
        }    
    
        .login-btn:active {    
            transform: translateY(0);    
        }    
    
        .demo-info {    
            background: #e3f2fd;    
            padding: 15px;    
            border-radius: 10px;    
            margin-bottom: 20px;    
            border-left: 4px solid #2196f3;    
        }    
    
        .demo-info h3 {    
            color: #1976d2;    
            margin-bottom: 10px;    
            font-size: 16px;    
        }    
    
        .demo-info p {    
            color: #555;    
            font-size: 14px;    
            margin-bottom: 5px;    
        }    
    
        .demo-info code {    
            background: #f5f5f5;    
            padding: 2px 6px;    
            border-radius: 4px;    
            font-family: 'Courier New', monospace;    
            color: #d32f2f;    
        }    
    
        .message {    
            margin-top: 15px;    
            padding: 10px;    
            border-radius: 8px;    
            text-align: center;    
            display: none;    
        }    
    
        .message.success {    
            background: #d4edda;    
            color: #155724;    
            border: 1px solid #c3e6cb;    
        }    
    
        .message.error {    
            background: #f8d7da;    
            color: #721c24;    
            border: 1px solid #f5c6cb;    
        }    
    
        .forgot-password {    
            text-align: center;    
            margin-top: 20px;    
        }    
    
        .forgot-password a {    
            color: #667eea;    
            text-decoration: none;    
            font-size: 14px;    
        }    
    
        .forgot-password a:hover {    
            text-decoration: underline;    
        }    
    </style>    
</head>    
<body>    
    <div class="login-container">    
        <div class="login-header">    
            <h1>ลงชื่อเข้าใช้งาน</h1>    
            <p>กรุณาใส่ชื่อผู้ใช้และรหัสผ่านของคุณ</p>    
        </div>    
    
        <div class="demo-info">    
            <h3>ข้อมูลสำหรับทดสอบ:</h3>    
            <p><strong>ชื่อผู้ใช้:</strong> <code>admin</code></p>    
            <p><strong>รหัสผ่าน:</strong> <code>????</code></p>    
        </div>    
    
        <form id="loginForm">    
            <div class="form-group">    
                <label for="username">ชื่อผู้ใช้:</label>    
                <input type="text" id="username" name="username" required>    
            </div>    
    
            <div class="form-group">    
                <label for="password">รหัสผ่าน:</label>    
                <input type="password" id="password" name="password" required>    
            </div>    
    
            <button type="submit" class="login-btn">เข้าสู่ระบบ</button>    
        </form>    
    
        <div id="message" class="message"></div>    
    
        <div class="forgot-password">    
            <a href="#" onclick="alert('นี่เป็นเพียงตัวอย่าง - ฟีเจอร์นี้ยังไม่ได้ทำงานจริง')">ลืมรหัสผ่าน?</a>    
        </div>    
    </div>    
    
    <script>    
        document.getElementById('loginForm').addEventListener('submit', function(e) {    
            e.preventDefault();    
                
            const username = document.getElementById('username').value;    
            const password = document.getElementById('password').value;    
            const messageDiv = document.getElementById('message');    
                
            // ข้อมูลสำหรับทดสอบ    
            const validUsername = 'admin';    
            const validPassword = '4643';    
                
            if (username === validUsername && password === validPassword) {    
                messageDiv.className = 'message success';    
                messageDiv.textContent = 'เข้าสู่ระบบสำเร็จ! ยินดีต้อนรับ ' + username;    
                messageDiv.style.display = 'block';    
                    
                // จำลองการเปลี่ยนหน้า    
                setTimeout(() => {    
                    alert('ยินดีต้อนรับเข้าสู่ระบบ! (นี่เป็นเพียงตัวอย่าง)');    
                }, 1000);    
                    
            } else {    
                messageDiv.className = 'message error';    
                messageDiv.textContent = 'ชื่อผู้ใช้หรือรหัสผ่านไม่ถูกต้อง กรุณาลองใหม่อีกครั้ง';    
                messageDiv.style.display = 'block';    
                    
                // ล้างรหัสผ่าน    
                document.getElementById('password').value = '';    
            }    
        });    
    
        // ซ่อนข้อความหลังจาก 5 วินาที    
        document.addEventListener('DOMContentLoaded', function() {    
            const messageDiv = document.getElementById('message');    
            if (messageDiv.style.display === 'block') {    
                setTimeout(() => {    
                    messageDiv.style.display = 'none';    
                }, 5000);    
            }    
        });    
    </script>    
</body>    
</html>    
    
