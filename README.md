<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق السند الاستثماري - تسجيل الدخول</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-color: #6a11cb;
            --secondary-color: #2575fc;
            --accent-color: #ff5722;
            --light-color: #f5f5f5;
            --dark-color: #333;
            --success-color: #2ecc71;
            --error-color: #e74c3c;
        }
        
        body {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: var(--dark-color);
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .android-app {
            width: 360px;
            height: 740px;
            background-color: white;
            border-radius: 40px;
            overflow: hidden;
            position: relative;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
        
        .status-bar {
            height: 25px;
            background-color: var(--primary-color);
            color: white;
            display: flex;
            justify-content: space-between;
            padding: 0 20px;
            align-items: center;
            font-size: 12px;
        }
        
        .header {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            padding: 20px;
            text-align: center;
            color: white;
            position: relative;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .app-content {
            height: calc(100% - 150px);
            overflow-y: auto;
            padding: 15px;
        }
        
        .user-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background-color: var(--light-color);
            border-radius: 10px;
            margin-bottom: 15px;
            display: none;
        }
        
        .points {
            display: flex;
            align-items: center;
            font-weight: bold;
            font-size: 18px;
        }
        
        .points i {
            color: gold;
            margin-left: 5px;
        }
        
        .counter-section, .wheel-section, .referral-section {
            background-color: var(--light-color);
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin-bottom: 15px;
            display: none;
        }
        
        .auth-section {
            background-color: var(--light-color);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            margin-bottom: 15px;
        }
        
        .section-title {
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-color);
            color: var(--primary-color);
            font-size: 18px;
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-left: 10px;
        }
        
        /* Circular Counter Styles */
        .circular-counter {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 0 auto;
        }
        
        .counter-bg {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: conic-gradient(var(--secondary-color) 0%, var(--primary-color) 100%);
            position: absolute;
        }
        
        .counter-inner {
            position: absolute;
            width: 160px;
            height: 160px;
            background: white;
            border-radius: 50%;
            top: 20px;
            left: 20px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        .counter-value {
            font-size: 28px;
            font-weight: bold;
            color: var(--primary-color);
        }
        
        .counter-label {
            font-size: 14px;
            color: var(--dark-color);
        }
        
        /* Wheel Styles */
        .wheel-container {
            position: relative;
            width: 220px;
            height: 220px;
            margin: 0 auto;
        }
        
        .wheel {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: conic-gradient(
                #ff7676 0deg 45deg, 
                #f6d365 45deg 90deg, 
                #a8edea 90deg 135deg, 
                #84fab0 135deg 180deg,
                #a1c4fd 180deg 225deg,
                #c2e9fb 225deg 270deg,
                #d4fc79 270deg 315deg,
                #ffecd2 315deg 360deg
            );
            position: relative;
            overflow: hidden;
            transition: transform 3s cubic-bezier(0.17, 0.67, 0.83, 0.67);
        }
        
        .wheel-item {
            position: absolute;
            width: 50%;
            height: 50%;
            transform-origin: bottom right;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--dark-color);
        }
        
        .wheel-button {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--accent-color);
            color: white;
            border: none;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            z-index: 10;
        }
        
        /* Form Styles */
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }
        
        .auth-options {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .auth-option {
            flex: 1;
            text-align: center;
            padding: 10px;
            background-color: #eee;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .auth-option.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .auth-form {
            display: none;
        }
        
        .auth-form.active {
            display: block;
        }
        
        button {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            border: none;
            border-radius: 5px;
            color: white;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            padding: 12px;
            width: 100%;
            transition: transform 0.3s, box-shadow 0.3s;
            margin-top: 10px;
        }
        
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.15);
        }
        
        .referral-code {
            background-color: #eee;
            padding: 15px;
            border-radius: 5px;
            text-align: center;
            font-size: 18px;
            font-weight: bold;
            letter-spacing: 2px;
            margin: 15px 0;
        }
        
        .bottom-nav {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: white;
            display: flex;
            justify-content: space-around;
            padding: 10px;
            border-top: 1px solid #ddd;
        }
        
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: #888;
            font-size: 12px;
        }
        
        .nav-item.active {
            color: var(--primary-color);
        }
        
        .nav-item i {
            font-size: 20px;
            margin-bottom: 5px;
        }
        
        .notification {
            position: absolute;
            top: 50px;
            right: 20px;
            left: 20px;
            padding: 15px 20px;
            background-color: var(--accent-color);
            color: white;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            transform: translateY(-150%);
            transition: transform 0.3s;
            z-index: 1000;
            text-align: center;
        }
        
        .notification.show {
            transform: translateY(0);
        }
        
        .splash-screen {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            transition: opacity 1s;
        }
        
        .splash-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }
        
        .app-name {
            color: white;
            font-size: 32px;
            font-weight: bold;
            margin-top: 20px;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        }
        
        .app-tagline {
            color: rgba(255, 255, 255, 0.8);
            margin-top: 10px;
        }
        
        .otp-section {
            display: none;
        }
        
        .otp-inputs {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .otp-inputs input {
            width: 50px;
            height: 50px;
            text-align: center;
            font-size: 20px;
            border: 2px solid #ddd;
            border-radius: 5px;
        }
        
        .resend-otp {
            text-align: center;
            margin-top: 10px;
            color: var(--primary-color);
            cursor: pointer;
        }
        
        .error-message {
            color: var(--error-color);
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }
        
        .user-actions {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
        }
        
        .user-actions button {
            width: 48%;
        }
        
        .logout-btn {
            background: linear-gradient(135deg, #e74c3c 0%, #c0392b 100%);
        }
        
        .login-switch {
            text-align: center;
            margin-top: 15px;
            color: var(--primary-color);
            cursor: pointer;
            font-weight: 500;
        }
    </style>
</head>
<body>
    <div class="android-app">
        <div class="status-bar">
            <span id="current-time">12:30</span>
            <span>
                <i class="fas fa-signal"></i>
                <i class="fas fa-wifi" style="margin: 0 5px;"></i>
                <i class="fas fa-battery-full"></i>
            </span>
        </div>
        
        <div class="splash-screen" id="splash-screen">
            <i class="fas fa-gem" style="font-size: 60px; color: white;"></i>
            <div class="app-name">السند الاستثماري</div>
            <div class="app-tagline">استثمر وقتك واحصل على المكافآت</div>
        </div>
        
        <div class="header">
            <div class="logo">
                <i class="fas fa-gem"></i> السند الاستثماري
            </div>
            <h2 id="main-heading">تسجيل الدخول إلى التطبيق</h2>
        </div>
        
        <div class="app-content">
            <div class="user-info" id="user-info">
                <div class="user">
                    <i class="fas fa-user"></i> <span id="user-name">مستخدم جديد</span>
                </div>
                <div class="points">
                    <span id="user-points">1500</span> 
                    <i class="fas fa-gem"></i>
                </div>
            </div>
            
            <div class="counter-section" id="counter-section">
                <h3 class="section-title">
                    <i class="fas fa-clock"></i> العدّاد اليومي
                </h3>
                <div class="circular-counter">
                    <div class="counter-bg" id="counter-bg"></div>
                    <div class="counter-inner">
                        <div class="counter-value" id="counter-value">18:42:11</div>
                        <div class="counter-label">للحصول التالي</div>
                    </div>
                </div>
                <button id="claim-btn" disabled>المطالبة بالجوائز</button>
                <p id="claim-message" style="text-align: center; margin-top: 10px; color: green; display: none;">
                    لقد حصلت على 500 جوهرة!
                </p>
            </div>
            
            <div class="wheel-section" id="wheel-section">
                <h3 class="section-title">
                    <i class="fas fa-dharmachakra"></i> عجلة الحظ
                </h3>
                <div class="wheel-container">
                    <div class="wheel" id="wheel">
                        <div class="wheel-item">50</div>
                        <div class="wheel-item">100</div>
                        <div class="wheel-item">200</div>
                        <div class="wheel-item">300</div>
                        <div class="wheel-item">150</div>
                        <div class="wheel-item">75</div>
                        <div class="wheel-item">250</div>
                        <div class="wheel-item">400</div>
                    </div>
                    <button class="wheel-button" id="spin-btn">
                        <i class="fas fa-redo"></i>
                    </button>
                </div>
                <p style="text-align: center; margin-top: 15px;">
                    لديك <span id="spins-remaining">3</span> محاولات متبقية
                </p>
            </div>
            
            <div class="referral-section" id="referral-section">
                <h3 class="section-title">
                    <i class="fas fa-share-alt"></i> رمز الإحالة
                </h3>
                <p>شارك رمز الإحالة الخاص بك مع أصدقائك واحصل على مكافآت مجانية!</p>
                <div class="referral-code" id="referral-code">X7F9K2</div>
                <div class="form-group">
                    <label>أدخل رمز الإحالة:</label>
                    <input type="text" id="referral-input" placeholder="أدخل الرمز هنا">
                    <div class="error-message" id="referral-error">رمز الإحالة غير صحيح</div>
                </div>
                <button id="apply-referral">تأكيد الرمز</button>
                <button id="share-referral" style="background-color: #25D366;">
                    <i class="fab fa-whatsapp"></i> مشاركة الرمز عبر واتساب
                </button>
            </div>
            
            <div class="auth-section" id="auth-section">
                <h3 class="section-title">
                    <i class="fas fa-user-lock"></i> <span id="auth-title">تسجيل الدخول</span>
                </h3>
                <div class="auth-options">
                    <div class="auth-option active" data-target="phone-form">رقم الهاتف</div>
                    <div class="auth-option" data-target="email-form">البريد الإلكتروني</div>
                </div>
                
                <div class="auth-form active" id="phone-form">
                    <div class="form-group">
                        <label>رقم الهاتف:</label>
                        <input type="tel" id="phone-number" placeholder="أدخل رقم هاتفك">
                        <div class="error-message" id="phone-error">رقم الهاتف غير صحيح</div>
                    </div>
                    <button id="send-otp">إرسال رمز التحقق</button>
                    
                    <div class="otp-section" id="phone-otp-section">
                        <div class="form-group">
                            <label>أدخل رمز التحقق:</label>
                            <div class="otp-inputs">
                                <input type="text" maxlength="1" class="otp-digit">
                                <input type="text" maxlength="1" class="otp-digit">
                                <input type="text" maxlength="1" class="otp-digit">
                                <input type="text" maxlength="1" class="otp-digit">
                                <input type="text" maxlength="1" class="otp-digit">
                                <input type="text" maxlength="1" class="otp-digit">
                            </div>
                        </div>
                        <button id="verify-otp">تحقق من الرمز</button>
                        <div class="resend-otp" id="resend-otp">إعادة إرسال الرمز</div>
                    </div>
                </div>
                
                <div class="auth-form" id="email-form">
                    <div class="form-group">
                        <label>البريد الإلكتروني:</label>
                        <input type="email" id="email" placeholder="أدخل بريدك الإلكتروني">
                        <div class="error-message" id="email-error">البريد الإلكتروني غير صحيح</div>
                    </div>
                    <div class="form-group">
                        <label>كلمة المرور:</label>
                        <input type="password" id="password" placeholder="أدخل كلمة المرور">
                        <div class="error-message" id="password-error">كلمة المرور يجب أن تكون 6 أحرف على الأقل</div>
                    </div>
                    <button id="login-btn">تسجيل الدخول</button>
                    <button id="register-btn" style="background-color: var(--accent-color);">إنشاء حساب جديد</button>
                </div>
                
                <div class="login-switch" id="login-switch">
                    هل لديك حساب already? <span id="switch-mode">إنشاء حساب جديد</span>
                </div>
            </div>

            <div class="user-actions" id="user-actions" style="display: none;">
                <button class="logout-btn" id="logout-btn">تسجيل الخروج</button>
                <button id="profile-btn">الملف الشخصي</button>
            </div>
        </div>
        
        <div class="bottom-nav">
            <div class="nav-item active">
                <i class="fas fa-home"></i>
                <span>الرئيسية</span>
            </div>
            <div class="nav-item">
                <i class="fas fa-gem"></i>
                <span>الجوائز</span>
            </div>
            <div class="nav-item">
                <i class="fas fa-history"></i>
                <span>السجل</span>
            </div>
            <div class="nav-item">
                <i class="fas fa-user"></i>
                <span>الحساب</span>
            </div>
        </div>
        
        <div class="notification" id="notification">
            <i class="fas fa-gift"></i> 
            <span id="notification-text">تهانينا! لقد فزت بجائزة.</span>
        </div>
    </div>

    <script>
        // عناصر DOM
        const counterBg = document.getElementById('counter-bg');
        const counterValue = document.getElementById('counter-value');
        const claimBtn = document.getElementById('claim-btn');
        const claimMessage = document.getElementById('claim-message');
        const wheel = document.getElementById('wheel');
        const spinBtn = document.getElementById('spin-btn');
        const spinsRemaining = document.getElementById('spins-remaining');
        const userPoints = document.getElementById('user-points');
        const userName = document.getElementById('user-name');
        const authOptions = document.querySelectorAll('.auth-option');
        const authForms = document.querySelectorAll('.auth-form');
        const notification = document.getElementById('notification');
        const notificationText = document.getElementById('notification-text');
        const splashScreen = document.getElementById('splash-screen');
        const phoneOtpSection = document.getElementById('phone-otp-section');
        const sendOtpBtn = document.getElementById('send-otp');
        const verifyOtpBtn = document.getElementById('verify-otp');
        const resendOtp = document.getElementById('resend-otp');
        const loginBtn = document.getElementById('login-btn');
        const registerBtn = document.getElementById('register-btn');
        const referralCode = document.getElementById('referral-code');
        const applyReferralBtn = document.getElementById('apply-referral');
        const shareReferralBtn = document.getElementById('share-referral');
        const currentTime = document.getElementById('current-time');
        const otpDigits = document.querySelectorAll('.otp-digit');
        const logoutBtn = document.getElementById('logout-btn');
        const userInfo = document.getElementById('user-info');
        const counterSection = document.getElementById('counter-section');
        const wheelSection = document.getElementById('wheel-section');
        const referralSection = document.getElementById('referral-section');
        const authSection = document.getElementById('auth-section');
        const userActions = document.getElementById('user-actions');
        const loginSwitch = document.getElementById('login-switch');
        const switchMode = document.getElementById('switch-mode');
        const authTitle = document.getElementById('auth-title');
        const mainHeading = document.getElementById('main-heading');
        
        // متغيرات التطبيق
        let countdown = 10; // 10 ثواني للتجربة (في التطبيق الحقيقي سيكون 24 ساعة)
        let canClaim = false;
        let spins = 3;
        let points = 1500;
        let isLoggedIn = false;
        let otpCode = "";
        let isLoginMode = true;
        
        // تحديث الوقت الحالي
        function updateCurrentTime() {
            const now = new Date();
            currentTime.textContent = now.toLocaleTimeString('ar-EG', { hour: '2-digit', minute: '2-digit' });
        }
        
        setInterval(updateCurrentTime, 1000);
        updateCurrentTime();
        
        // إخفاء شاشة البداية بعد 3 ثوان
        setTimeout(() => {
            splashScreen.classList.add('hidden');
        }, 3000);
        
        // تبديل بين وضع تسجيل الدخول وإنشاء حساب
        switchMode.addEventListener('click', function() {
            isLoginMode = !isLoginMode;
            
            if (isLoginMode) {
                authTitle.textContent = 'تسجيل الدخول';
                loginBtn.style.display = 'block';
                registerBtn.style.display = 'none';
                switchMode.textContent = 'إنشاء حساب جديد';
                document.querySelectorAll('.auth-form').forEach(form => {
                    const passwordGroup = form.querySelector('input[type="password"]');
                    if (passwordGroup) {
                        passwordGroup.closest('.form-group').style.display = 'block';
                    }
                });
            } else {
                authTitle.textContent = 'إنشاء حساب جديد';
                loginBtn.style.display = 'none';
                registerBtn.style.display = 'block';
                switchMode.textContent = 'تسجيل الدخول';
                document.querySelectorAll('.auth-form').forEach(form => {
                    const passwordGroup = form.querySelector('input[type="password"]');
                    if (passwordGroup) {
                        passwordGroup.closest('.form-group').style.display = 'block';
                    }
                });
            }
        });
        
        // إدارة إدخال رمز OTP
        otpDigits.forEach((digit, index) => {
            digit.addEventListener('input', () => {
                if (digit.value.length === 1 && index < otpDigits.length - 1) {
                    otpDigits[index + 1].focus();
                }
            });
            
            digit.addEventListener('keydown', (e) => {
                if (e.key === 'Backspace' && digit.value === '' && index > 0) {
                    otpDigits[index - 1].focus();
                }
            });
        });
        
        // إرسال رمز OTP
        sendOtpBtn.addEventListener('click', function() {
            const phoneNumber = document.getElementById('phone-number').value;
            
            if (phoneNumber.length < 10) {
                showNotification('يرجى إدخال رقم هاتف صحيح');
                return;
            }
            
            // في تطبيق حقيقي، سيتم إرسال الرمز إلى الخادم
            // هنا نقوم بمحاكاة إنشاء رمز عشوائي
            otpCode = Math.floor(100000 + Math.random() * 900000).toString();
            showNotification('تم إرسال رمز التحقق إلى هاتفك: ' + otpCode);
            
            // إظهار قسم إدخال الرمز
            phoneOtpSection.style.display = 'block';
            sendOtpBtn.style.display = 'none';
        });
        
        // إعادة إرسال رمز OTP
        resendOtp.addEventListener('click', function() {
            otpCode = Math.floor(100000 + Math.random() * 900000).toString();
            showNotification('تم إعادة إرسال رمز التحقق: ' + otpCode);
        });
        
        // التحقق من رمز OTP
        verifyOtpBtn.addEventListener('click', function() {
            let enteredOtp = "";
            otpDigits.forEach(digit => {
                enteredOtp += digit.value;
            });
            
            if (enteredOtp === otpCode) {
                showNotification('تم تسجيل الدخول بنجاح!');
                isLoggedIn = true;
                userName.textContent = document.getElementById('phone-number').value;
                
                // تحديث واجهة المستخدم بعد تسجيل الدخول
                updateUIAfterLogin();
                
                // إنشاء رمز إحالة فريد للمستخدم
                generateReferralCode();
            } else {
                showNotification('رمز التحقق غير صحيح!');
            }
        });
        
        // تسجيل الدخول بالبريد الإلكتروني
        loginBtn.addEventListener('click', function() {
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            if (!validateEmail(email)) {
                showNotification('يرجى إدخال بريد إلكتروني صحيح');
                return;
            }
            
            if (password.length < 6) {
                showNotification('كلمة المرور يجب أن تكون 6 أحرف على الأقل');
                return;
            }
            
            // محاكاة تسجيل الدخول
            showNotification('تم تسجيل الدخول بنجاح!');
            isLoggedIn = true;
            userName.textContent = email;
            
            // تحديث واجهة المستخدم بعد تسجيل الدخول
            updateUIAfterLogin();
            
            // إنشاء رمز إحالة فريد للمستخدم
            generateReferralCode();
        });
        
        // إنشاء حساب بالبريد الإلكتروني
        registerBtn.addEventListener('click', function() {
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            if (!validateEmail(email)) {
                showNotification('يرجى إدخال بريد إلكتروني صحيح');
                return;
            }
            
            if (password.length < 6) {
                showNotification('كلمة المرور يجب أن تكون 6 أحرف على الأقل');
                return;
            }
            
            // محاكاة إنشاء حساب
            showNotification('تم إنشاء الحساب بنجاح!');
            isLoggedIn = true;
            userName.textContent = email;
            
            // تحديث واجهة المستخدم بعد تسجيل الدخول
            updateUIAfterLogin();
            
            // إنشاء رمز إحالة فريد للمستخدم
            generateReferralCode();
        });
        
        // تطبيق رمز الإحالة
        applyReferralBtn.addEventListener('click', function() {
            const referralInput = document.getElementById('referral-input').value;
            
            if (referralInput.length !== 6) {
                showNotification('يرجى إدخال رمز إحالة صحيح (6 أحرف)');
                return;
            }
            
            // محاكاة تطبيق رمز الإحالة
            points += 200;
            userPoints.textContent = points;
            showNotification('تم تطبيق رمز الإحالة بنجاح! حصلت على 200 جوهرة إضافية');
        });
        
        // مشاركة رمز الإحالة
        shareReferralBtn.addEventListener('click', function() {
            // في تطبيق حقيقي، سيتم مشاركة الرمز عبر واتساب
            showNotification('تم نسخ رمز الإحالة: ' + referralCode.textContent);
            
            // محاكاة نسخ الرمز إلى الحافظة
            navigator.clipboard.writeText(referralCode.textContent)
                .then(() => {
                    showNotification('تم نسخ رمز الإحالة: ' + referralCode.textContent);
                })
                .catch(err => {
                    showNotification('لم يتمكن التطبيق من نسخ الرمز');
                });
        });
        
        // تسجيل الخروج
        logoutBtn.addEventListener('click', function() {
            isLoggedIn = false;
            showNotification('تم تسجيل الخروج بنجاح');
            
            // إعادة تعيين واجهة المستخدم
            userInfo.style.display = 'none';
            counterSection.style.display = 'none';
            wheelSection.style.display = 'none';
            referralSection.style.display = 'none';
            authSection.style.display = 'block';
            userActions.style.display = 'none';
            userName.textContent = 'مستخدم جديد';
            mainHeading.textContent = 'تسجيل الدخول إلى التطبيق';
            
            // إعادة تعيين النماذج
            document.getElementById('phone-number').value = '';
            document.getElementById('email').value = '';
            document.getElementById('password').value = '';
            document.getElementById('referral-input').value = '';
            otpDigits.forEach(digit => digit.value = '');
            phoneOtpSection.style.display = 'none';
            sendOtpBtn.style.display = 'block';
        });
        
        // تحقق من صحة البريد الإلكتروني
        function validateEmail(email) {
            const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return re.test(email);
        }
        
        // توليد رمز إحالة عشوائي
        function generateReferralCode() {
            const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            let result = '';
            for (let i = 0; i < 6; i++) {
                result += characters.charAt(Math.floor(Math.random() * characters.length));
            }
            referralCode.textContent = result;
            return result;
        }
        
        // تحديث واجهة المستخدم بعد تسجيل الدخول
        function updateUIAfterLogin() {
            userInfo.style.display = 'flex';
            counterSection.style.display = 'block';
            wheelSection.style.display = 'block';
            referralSection.style.display = 'block';
            authSection.style.display = 'none';
            userActions.style.display = 'flex';
            mainHeading.textContent = 'احصل على 500 جوهرة كل 24 ساعة';
        }
        
        // تحديث العداد
        function updateCounter() {
            const hours = Math.floor(countdown / 3600);
            const minutes = Math.floor((countdown % 3600) / 60);
            const seconds = countdown % 60;
            
            counterValue.textContent = `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
            
            // تحديث الخلفية الدائرية
            const percentage = (countdown / 86400) * 100; // 86400 ثانية في 24 ساعة
            counterBg.style.background = `conic-gradient(var(--secondary-color) 0%, var(--primary-color) ${100 - percentage}%, #eee ${100 - percentage}% 100%)`;
            
            if (countdown > 0) {
                countdown--;
                setTimeout(updateCounter, 1000);
            } else {
                canClaim = true;
                claimBtn.disabled = false;
                counterValue.textContent = "جاهز!";
                claimBtn.textContent = "المطالبة بـ 500 جوهرة";
            }
        }
        
        // المطالبة بالمكافأة
        claimBtn.addEventListener('click', function() {
            if (canClaim && isLoggedIn) {
                points += 500;
                userPoints.textContent = points;
                claimMessage.style.display = 'block';
                claimBtn.disabled = true;
                canClaim = false;
                
                // إعادة تعيين العداد
                countdown = 86400; // 24 ساعة
                setTimeout(updateCounter, 2000);
                
                // إظهار الإشعار
                showNotification('تهانينا! لقد حصلت على 500 جوهرة.');
            } else if (!isLoggedIn) {
                showNotification('يجب تسجيل الدخول أولاً للمطالبة بالجوائز');
            }
        });
        
        // تدوير عجلة الحظ
        spinBtn.addEventListener('click', function() {
            if (spins > 0 && isLoggedIn) {
                spinBtn.disabled = true;
                const degrees = 1080 + Math.floor(Math.random() * 360); // 3 دورات كاملة + عشوائي
                wheel.style.transform = `rotate(${degrees}deg)`;
                
                // حساب الجائزة بناء على درجة الدوران
                setTimeout(function() {
                    const segment = 45; // 45 درجة لكل قطاع (360/8)
                    const actualDegrees = degrees % 360;
                    const winningSegment = Math.floor(actualDegrees / segment);
                    
                    const prizes = [50, 100, 200, 300, 150, 75, 250, 400];
                    const prize = prizes[winningSegment];
                    
                    points += prize;
                    userPoints.textContent = points;
                    spins--;
                    spinsRemaining.textContent = spins;
                    
                    showNotification(`تهانينا! لقد فزت بــ ${prize} جوهرة.`);
                    
                    if (spins === 0) {
                        spinBtn.innerHTML = '<i class="fas fa-times"></i>';
                    } else {
                        spinBtn.disabled =- `// Find race conditions in this async code`
  <sub>Concurrent systems in JS, Python, Go, etc.</sub>

- `// Add print statements to trace the execution flow of this Python script...`
  <sub>For debugging complex Python scripts or understanding unexpected behavior.</sub>


## Documentation

- `// Write a README for this project`
  <sub>Any repo lacking a basic project overview.</sub>

- `// Add comments to this code`
  <sub>Improves maintainability of complex logic.</sub>

- `// Write API docs for this endpoint`
  <sub>REST or GraphQL backends.</sub>

- `// Generate Sphinx-style docstrings for this Python module/class/function...`
  <sub>Ideal for Python projects using Sphinx for documentation generation.</sub>



## Testing

- `// Add integration tests for this API endpoint`
  <sub>Express, FastAPI, Django, Flask apps.</sub>

- `// Write a test that mocks fetch`
  <sub>Browser-side fetch or axios logic.</sub>

- `// Convert this test from Mocha to Jest`
  <sub>JS test suite migrations.</sub>

- `// Generate property-based tests for this function`
  <sub>Functional or logic-heavy code.</sub>

- `// Simulate slow network conditions in this test suite`
  <sub>Web and mobile apps.</sub>

- `// Write a test to ensure backward compatibility for this function`
  <sub>Library or SDK maintainers.</sub>

- `// Write a Pytest fixture to mock this external API call...`
  <sub>For Python projects using Pytest and needing robust mocking for testing.</sub>



## Package Management

- `// Upgrade my linter and autofix breaking config changes`
  <sub>JS/TS repos using ESLint or Prettier.</sub>

- `// Show me the changelog for React 19`
  <sub>Web frontend apps using React.</sub>

- `// Which dependencies can I safely remove?`
  <sub>Bloated or legacy codebases.</sub>

- `// Check if these packages are still maintained`
  <sub>Security-conscious or long-term projects.</sub>

- `// Set up Renovate or Dependabot for auto-updates`
  <sub>Best for active projects with CI/CD.</sub>



## AI-Native Tasks

- `// Analyze this repo and generate 3 feature ideas`
  <sub>Vision-stage or greenfield products.</sub>

- `// Identify tech debt in this file`
  <sub>Codebases with messy or fragile logic.</sub>

- `// Find duplicate logic across files`
  <sub>Sprawling repos lacking DRY practices.</sub>

- `// Cluster related functions and suggest refactors`
  <sub>Projects with lots of utils or helpers.</sub>

- `// Help me scope this issue so Jules can solve it`
  <sub>For working with Jules on real issues.</sub>

- `// Convert this function into a reusable plugin/module`
  <sub>Componentizing logic-heavy code.</sub>

- `// Refactor this Python function to be more amenable to parallel processing (e.g., using multiprocessing or threading)...`
  <sub>For optimizing performance in computationally intensive Python applications.</sub>



## Context

- `// Write a status update based on recent commits`
  <sub>Managerial and async communication.</sub>

- `// Summarize all changes in the last 7 days`
  <sub>Catching up after time off.</sub>



## Fun & Experimental

- `// Add a confetti animation when {a specific} action succeeds`
  <sub>Frontend web apps with user delight moments.</sub>

- `// Inject a developer joke when {a specific} build finishes`
  <sub>Personal projects or team tools.</sub>

- `// Build a mini CLI game that runs in the terminal`
  <sub>For learning or community fun.</sub>

- `// Add a dark mode Easter egg to this UI`
  <sub>Design-heavy frontend projects.</sub>

- `// Turn this tool into a GitHub App`
  <sub>Reusable, platform-integrated tools.</sub>

## Start from Scratch

- `// What's going on in this repo?`
  <sub>Great for legacy repos or onboarding onto unfamiliar code.</sub>

- `// Initialize a new Express app with CORS enabled`
  <sub>Web backend projects using Node.js and Express.</sub>

- `// Set up a monorepo using Turborepo and PNPM`
  <sub>Multi-package JS/TS projects with shared dependencies.</sub>

- `// Bootstrap a Python project with Poetry and Pytest`
  <sub>Python repos aiming for clean dependency and test setup.</sub>

- `// Create a starter template for a Chrome extension`
  <sub>Browser extension development.</sub>

- `// I want to build a web scraper—start me off`
  <sub>Data scraping or automation tools using Python/Node.</sub>



## Contributing

Your contributions are welcome! Add new prompts, fix formatting, or suggest categories.

- 📄 [Contributing Guide](contributing.md)
- 🪄 Open a [Pull Request](https://github.com/YOUR_REPO/pulls)
