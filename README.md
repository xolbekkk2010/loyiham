# loyiham
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart-Uy Sozlovchisi | Kelajak Sizning Qo'lingizda</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #4facfe;
            --secondary-color: #00f2fe;
            --dark-bg: #0f172a;
            --card-bg: #1e293b;
            --text-color: #f8fafc;
            --accent-color: #22c55e;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header */
        header {
            height: 100vh;
            background: linear-gradient(135deg, rgba(15,23,42,0.9), rgba(15,23,42,0.7)), 
                        url('https://images.unsplash.com/photo-1558002038-1055907df827?auto=format&fit=crop&q=80&w=1920');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeInDown 1s ease;
        }

        .btn {
            padding: 15px 40px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            border: none;
            border-radius: 50px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            text-decoration: none;
        }

        .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(79, 172, 254, 0.4);
        }

        /* Dashboard Preview Section */
        .container {
            max-width: 1200px;
            margin: -100px auto 50px;
            padding: 0 20px;
        }

        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .card:hover {
            border-color: var(--primary-color);
            transform: translateY(-5px);
        }

        .status {
            display: inline-block;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            margin-right: 10px;
        }

        .on { background-color: var(--accent-color); box-shadow: 0 0 10px var(--accent-color); }
        .off { background-color: #ef4444; }

        /* Switch Styling */
        .switch {
            position: relative;
            display: inline-block;
            width: 60px;
            height: 34px;
            float: right;
        }

        .switch input { display: none; }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0; left: 0; right: 0; bottom: 0;
            background-color: #334155;
            transition: .4s;
            border-radius: 34px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 26px; width: 26px;
            left: 4px; bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider { background-color: var(--primary-color); }
        input:checked + .slider:before { transform: translateX(26px); }

        /* Contact Form */
        .contact-section {
            background: var(--card-bg);
            padding: 80px 20px;
            text-align: center;
        }

        form {
            max-width: 600px;
            margin: 40px auto;
            display: grid;
            gap: 20px;
        }

        input, textarea {
            width: 100%;
            padding: 15px;
            border-radius: 10px;
            border: 1px solid #334155;
            background: #0f172a;
            color: white;
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        footer {
            padding: 30px;
            text-align: center;
            font-size: 0.9rem;
            opacity: 0.7;
        }
    </style>
</head>
<body>

    <header>
        <h1>Smart-Uy Sozlovchisi</h1>
        <p style="font-size: 1.2rem; margin-bottom: 30px;">Uyingizni aqlli va xavfsiz qilishga yordam beramiz</p>
        <a href="#booking" class="btn">Bepul Konsultatsiya</a>
    </header>

    <div class="container">
        <h2 style="margin-bottom: 30px; text-align: center;">Tizimni Boshqarish (Demo)</h2>
        <div class="dashboard-grid">
            <div class="card" id="living-room">
                <span class="status on" id="status-1"></span>
                <span id="text-1">Yashash xonasi chiroqlari</span>
                <label class="switch">
                    <input type="checkbox" checked onchange="toggleDevice(1)">
                    <span class="slider"></span>
                </label>
                <p style="margin-top: 15px; font-size: 0.8rem; color: #94a3b8;">Energiya sarfi: 12W</p>
            </div>

            <div class="card" id="ac-unit">
                <span class="status off" id="status-2"></span>
                <span id="text-2">Konditsioner tizimi</span>
                <label class="switch">
                    <input type="checkbox" onchange="toggleDevice(2)">
                    <span class="slider"></span>
                </label>
                <p style="margin-top: 15px; font-size: 0.8rem; color: #94a3b8;">Harorat: 24°C</p>
            </div>

            <div class="card">
                <span class="status on"></span>
                <span>Xavfsizlik kamerasi</span>
                <p style="margin-top: 15px; font-size: 0.8rem; color: var(--accent-color);">Jonli efir: Faol</p>
                <button class="btn" style="padding: 5px 15px; margin-top: 10px; font-size: 0.7rem;">Ko'rish</button>
            </div>
        </div>
    </div>

    <section class="contact-section" id="booking">
        <h2>Xizmatga Buyurtma Berish</h2>
        <p>Ma'lumotlaringizni qoldiring, biz sizga uyingizni aqlli qilishga yordam beramiz</p>
        <form id="contactForm">
            <input type="text" placeholder="Ismingiz" required>
            <input type="tel" placeholder="Telefon raqamingiz (+998...)" required>
            <textarea rows="4" placeholder="Qaysi qurilmalarni o'rnatish kerak? (Chiroq, Kamera, Isitish tizimi...)"></textarea>
            <button type="submit" class="btn">Yuborish</button>
        </form>
    </section>

    <footer>
        &copy; 2024 Smart-Uy Sozlovchisi. Barcha huquqlar himoyalangan.
    </footer>

    <script>
        // Qurilmalarni yoqish/o'chirish funksiyasi
        function toggleDevice(id) {
            const statusCircle = document.getElementById(`status-${id}`);
            const text = document.getElementById(`text-${id}`);
            
            if(statusCircle.classList.contains('on')) {
                statusCircle.classList.remove('on');
                statusCircle.classList.add('off');
                console.log(`Device ${id} o'chirildi`);
            } else {
                statusCircle.classList.remove('off');
                statusCircle.classList.add('on');
                console.log(`Device ${id} yoqildi`);
            }
        }

        // Formani qayta ishlash
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Rahmat! Sizning so\'rovingiz qabul qilindi. Tez orada mutaxassisimiz bog\'lanadi.');
            this.reset();
        });

        // Scroll animatsiyasi (oddiy variant)
        window.addEventListener('scroll', () => {
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                const cardTop = card.getBoundingClientRect().top;
                if(cardTop < window.innerHeight - 100) {
                    card.style.opacity = '1';
                }
            });
        });
    </script>
</body>
</html>
