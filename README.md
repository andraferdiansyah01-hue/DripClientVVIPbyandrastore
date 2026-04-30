```html
<!DOCTYPE html>
<html lang="id" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>ANDRA STORE App</title>
    
    <!-- PWA Meta Tags -->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="theme-color" content="#0a0f1d">
    <link rel="icon" type="image/png" href="1000013847.png">
    
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: '#3b82f6',
                        dark: {
                            bg: '#0a0f1d',
                            card: '#111827',
                            input: '#1f2937',
                            item: '#161e2d'
                        }
                    }
                }
            }
        }
    </script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap');
        
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-tap-highlight-color: transparent;
            overscroll-behavior-y: contain;
            transition: background-color 0.3s ease;
        }

        .safe-area-bottom {
            padding-bottom: env(safe-area-inset-bottom);
        }

        .active-tab {
            color: #3b82f6;
            transform: translateY(-2px);
            transition: all 0.3s ease;
        }

        .item-card {
            transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .item-card.active {
            border: 2px solid #3b82f6 !important;
            background-color: rgba(59, 130, 246, 0.1);
            transform: scale(1.02);
        }

        .page {
            display: none;
            animation: slideUp 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .page.active {
            display: block;
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        ::-webkit-scrollbar {
            display: none;
        }
        
        .glass-nav {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }
        .dark .glass-nav {
            background: rgba(10, 15, 29, 0.8);
        }

        .banner-container {
            position: relative;
            width: 100%;
            aspect-ratio: 16/9;
            border-radius: 2rem;
            overflow: hidden;
            margin-bottom: 2rem;
            box-shadow: 0 25px 50px -12px rgba(59, 130, 246, 0.25);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
    </style>
</head>
<body class="bg-slate-50 dark:bg-dark-bg text-slate-900 dark:text-white min-h-screen">

    <!-- Top Bar -->
    <header class="fixed top-0 left-0 right-0 z-50 glass-nav border-b border-slate-200 dark:border-gray-800 px-6 py-4 flex justify-between items-center">
        <div class="flex items-center gap-3">
            <div class="w-9 h-9 rounded-full border-2 border-blue-500 overflow-hidden shadow-lg shadow-blue-500/20">
                <img src="1000013847.png" alt="ANDRA STORE" class="w-full h-full object-cover">
            </div>
            <h1 class="font-extrabold text-lg tracking-tight bg-gradient-to-r from-blue-600 to-indigo-500 bg-clip-text text-transparent dark:from-blue-400 dark:to-indigo-300">ANDRA STORE</h1>
        </div>
        <button onclick="toggleTheme()" class="w-10 h-10 flex items-center justify-center rounded-2xl bg-slate-100 dark:bg-dark-card transition-all active:scale-90 border border-slate-200 dark:border-gray-700">
            <i id="theme-icon" class="fa-solid fa-moon text-blue-500"></i>
        </button>
    </header>

    <!-- Main Content Area -->
    <main class="pt-24 pb-32 px-4 max-w-lg mx-auto">
        
        <!-- Page: Home/Store -->
        <div id="page-home" class="page active">
            <!-- Product Banner -->
            <div class="banner-container">
                <img src="1000053435.jpg" alt="Drip Client Banner" class="w-full h-full object-cover">
                <div class="absolute inset-0 bg-gradient-to-t from-dark-bg/60 via-transparent to-transparent pointer-events-none"></div>
                <div class="absolute bottom-4 left-6">
                    <span class="bg-blue-600 text-[10px] font-black px-3 py-1 rounded-full text-white shadow-lg">PREMIUM MOD</span>
                </div>
            </div>

            <!-- Buyer Data Form -->
            <div class="bg-white dark:bg-dark-card rounded-[2rem] p-7 border border-slate-200 dark:border-gray-800 mb-6 shadow-sm">
                <div class="flex items-center gap-3 mb-5">
                    <div class="w-8 h-8 rounded-xl bg-blue-500/10 flex items-center justify-center">
                        <i class="fa-solid fa-id-card text-blue-500 text-sm"></i>
                    </div>
                    <h3 class="text-sm font-bold uppercase tracking-widest opacity-70">Identitas Pembeli</h3>
                </div>
                <div class="space-y-4">
                    <div class="relative">
                        <input type="text" id="app-nama" placeholder="Masukkan Nama Lengkap" class="w-full bg-slate-50 dark:bg-dark-input p-4 pl-12 rounded-2xl border border-slate-200 dark:border-gray-700 focus:ring-2 focus:ring-blue-500 outline-none transition-all placeholder:text-slate-400">
                        <i class="fa-solid fa-user absolute left-4 top-1/2 -translate-y-1/2 text-slate-400"></i>
                    </div>
                    <div class="relative">
                        <input type="tel" id="app-wa" placeholder="Nomor WhatsApp (Aktif)" class="w-full bg-slate-50 dark:bg-dark-input p-4 pl-12 rounded-2xl border border-slate-200 dark:border-gray-700 focus:ring-2 focus:ring-blue-500 outline-none transition-all placeholder:text-slate-400">
                        <i class="fa-solid fa-phone absolute left-4 top-1/2 -translate-y-1/2 text-slate-400"></i>
                    </div>
                </div>
            </div>

            <!-- Price Grid -->
            <div class="mb-8">
                <div class="flex items-center gap-3 mb-5 ml-2">
                    <div class="w-8 h-8 rounded-xl bg-amber-500/10 flex items-center justify-center">
                        <i class="fa-solid fa-crown text-amber-500 text-sm"></i>
                    </div>
                    <h3 class="text-sm font-bold uppercase tracking-widest opacity-70">Pilih Lisensi</h3>
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div onclick="selectAppItem(this, '1 Day', 20000)" class="item-card bg-white dark:bg-dark-card p-6 rounded-[2rem] border border-slate-200 dark:border-gray-800 text-center cursor-pointer shadow-sm">
                        <div class="text-[10px] font-black text-slate-400 dark:text-gray-500 mb-1 tracking-wider">STARTER</div>
                        <div class="text-xl font-black">1 DAY</div>
                        <div class="text-blue-500 font-bold mt-2 text-sm italic">Rp 20.000</div>
                    </div>
                    <div onclick="selectAppItem(this, '3 Day', 35000)" class="item-card bg-white dark:bg-dark-card p-6 rounded-[2rem] border border-slate-200 dark:border-gray-800 text-center cursor-pointer shadow-sm">
                        <div class="text-[10px] font-black text-slate-400 dark:text-gray-500 mb-1 tracking-wider">PRO</div>
                        <div class="text-xl font-black">3 DAY</div>
                        <div class="text-blue-500 font-bold mt-2 text-sm italic">Rp 35.000</div>
                    </div>
                    <div onclick="selectAppItem(this, '7 Day', 65000)" class="item-card bg-white dark:bg-dark-card p-6 rounded-[2rem] border border-slate-200 dark:border-gray-800 text-center cursor-pointer shadow-sm">
                        <div class="text-[10px] font-black text-slate-400 dark:text-gray-500 mb-1 tracking-wider">ELITE</div>
                        <div class="text-xl font-black">7 DAY</div>
                        <div class="text-blue-500 font-bold mt-2 text-sm italic">Rp 65.000</div>
                    </div>
                    <div onclick="selectAppItem(this, '30 Day', 160000)" class="item-card bg-white dark:bg-dark-card p-6 rounded-[2rem] border border-slate-200 dark:border-gray-800 text-center cursor-pointer shadow-sm">
                        <div class="text-[10px] font-black text-slate-400 dark:text-gray-500 mb-1 tracking-wider">ULTIMATE</div>
                        <div class="text-xl font-black">30 DAY</div>
                        <div class="text-blue-500 font-bold mt-2 text-sm italic">Rp 160.000</div>
                    </div>
                </div>
            </div>

            <!-- Checkout Section -->
            <div id="checkout-drawer" class="bg-blue-600 rounded-[2.5rem] p-7 shadow-2xl shadow-blue-600/30">
                <div class="flex justify-between items-center mb-6">
                    <div>
                        <p class="text-[10px] font-black text-blue-100 uppercase tracking-[0.2em] mb-1">Estimasi Harga</p>
                        <h4 id="app-total-display" class="text-3xl font-black text-white">Rp 0</h4>
                    </div>
                    <div class="text-right">
                        <span id="app-varian-display" class="bg-white/20 text-white text-[10px] font-bold px-3 py-1 rounded-lg">-</span>
                        <p class="text-[10px] text-blue-100 mt-2 font-bold uppercase">Drip Client FF</p>
                    </div>
                </div>
                <button onclick="prosesPesananApp()" class="w-full bg-white text-blue-600 font-black py-5 rounded-2xl shadow-xl active:scale-95 transition-all flex items-center justify-center gap-3">
                    <i class="fa-brands fa-whatsapp text-xl"></i>
                    ORDER VIA WHATSAPP
                </button>
            </div>
        </div>

        <!-- Page: Info -->
        <div id="page-info" class="page">
            <h2 class="text-3xl font-black mb-8 italic tracking-tighter">INFORMASI</h2>
            <div class="space-y-5">
                <!-- NEW: WhatsApp Channel Link -->
                <a href="https://whatsapp.com/channel/0029VbCVIUG2Jl87BRDQWn11" target="_blank" class="block bg-gradient-to-br from-green-500 to-emerald-600 p-7 rounded-[2.5rem] shadow-lg shadow-green-500/20 active:scale-[0.98] transition-all">
                    <div class="flex items-center justify-between mb-4">
                        <div class="w-10 h-10 rounded-2xl bg-white/20 flex items-center justify-center">
                            <i class="fa-solid fa-bullhorn text-white"></i>
                        </div>
                        <i class="fa-solid fa-arrow-up-right-from-square text-white/50 text-xs"></i>
                    </div>
                    <h4 class="font-black mb-1 text-lg text-white tracking-tight">Saluran WhatsApp</h4>
                    <p class="text-sm text-green-50/80 leading-relaxed font-medium">Klik di sini untuk bergabung dengan saluran informasi resmi ANDRA STORE.</p>
                </a>

                <div class="bg-white dark:bg-dark-card p-7 rounded-[2.5rem] border border-slate-200 dark:border-gray-800 shadow-sm">
                    <div class="w-10 h-10 rounded-2xl bg-blue-500/10 flex items-center justify-center mb-4">
                        <i class="fa-solid fa-circle-question text-blue-500"></i>
                    </div>
                    <h4 class="font-black mb-2 text-lg">Cara Order?</h4>
                    <p class="text-sm text-slate-500 dark:text-gray-400 leading-relaxed">Pilih paket lisensi yang diinginkan, isi form nama, lalu klik tombol Order. Kamu akan diarahkan ke WhatsApp untuk melakukan pembayaran dan menerima lisensi.</p>
                </div>
                <div class="bg-white dark:bg-dark-card p-7 rounded-[2.5rem] border border-slate-200 dark:border-gray-800 shadow-sm">
                    <div class="w-10 h-10 rounded-2xl bg-green-500/10 flex items-center justify-center mb-4">
                        <i class="fa-solid fa-shield-halved text-green-500"></i>
                    </div>
                    <h4 class="font-black mb-2 text-lg">Keamanan Akun</h4>
                    <p class="text-sm text-slate-500 dark:text-gray-400 leading-relaxed">Drip Client didesain dengan proteksi tingkat tinggi. Namun kami tetap menyarankan penggunaan yang bijak pada akun guest terlebih dahulu.</p>
                </div>
            </div>
        </div>
    </main>

    <!-- Bottom Navigation Bar -->
    <nav class="fixed bottom-0 left-0 right-0 glass-nav border-t border-slate-200 dark:border-gray-800 px-10 py-4 safe-area-bottom z-50">
        <div class="flex justify-between items-center max-w-sm mx-auto">
            <button onclick="switchPage('home')" id="tab-home" class="flex flex-col items-center gap-1 active-tab">
                <i class="fa-solid fa-house-chimney text-xl"></i>
                <span class="text-[9px] font-black uppercase tracking-widest mt-1">Store</span>
            </button>
            <button onclick="switchPage('info')" id="tab-info" class="flex flex-col items-center gap-1 text-slate-400">
                <i class="fa-solid fa-layer-group text-xl"></i>
                <span class="text-[9px] font-black uppercase tracking-widest mt-1">Info</span>
            </button>
            <a href="https://wa.me/6283897761639" target="_blank" class="flex flex-col items-center gap-1 text-slate-400">
                <i class="fa-solid fa-headset text-xl"></i>
                <span class="text-[9px] font-black uppercase tracking-widest mt-1">Admin</span>
            </a>
        </div>
    </nav>

    <!-- Notification Toast -->
    <div id="app-toast" class="fixed top-24 left-1/2 -translate-x-1/2 bg-slate-900 dark:bg-white text-white dark:text-dark-bg px-8 py-3 rounded-full text-xs font-black hidden z-[100] shadow-2xl transition-all">
        Pesan
    </div>

    <script>
        let currentAppVarian = "";
        let currentAppHarga = 0;

        function toggleTheme() {
            const isDark = document.documentElement.classList.toggle('dark');
            const icon = document.getElementById('theme-icon');
            icon.classList.replace(isDark ? 'fa-sun' : 'fa-moon', isDark ? 'fa-moon' : 'fa-sun');
            localStorage.setItem('app-theme', isDark ? 'dark' : 'light');
        }

        function switchPage(pageId) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page-' + pageId).classList.add('active');
            
            document.querySelectorAll('nav button').forEach(b => {
                b.classList.remove('active-tab');
                b.classList.add('text-slate-400');
            });
            document.getElementById('tab-' + pageId).classList.remove('text-slate-400');
            document.getElementById('tab-' + pageId).classList.add('active-tab');
            
            window.scrollTo(0, 0);
        }

        function selectAppItem(el, varian, harga) {
            currentAppVarian = varian;
            currentAppHarga = harga;
            
            document.querySelectorAll('.item-card').forEach(c => c.classList.remove('active'));
            el.classList.add('active');
            
            document.getElementById('app-total-display').innerText = 'Rp ' + harga.toLocaleString('id-ID');
            document.getElementById('app-varian-display').innerText = varian;
            
            if (window.navigator.vibrate) window.navigator.vibrate(20);
        }

        function showToast(msg) {
            const toast = document.getElementById('app-toast');
            toast.innerText = msg;
            toast.classList.remove('hidden');
            setTimeout(() => toast.classList.add('hidden'), 3000);
        }

        function prosesPesananApp() {
            const nama = document.getElementById('app-nama').value;
            const wa = document.getElementById('app-wa').value;
            const admin = "6283897761639";

            if (!nama) return showToast("MASUKKAN NAMA LENGKAP!");
            if (!currentAppVarian) return showToast("PILIH LISENSI!");

            const teks = `*FORM PESANAN ANDRA STORE*%0A` +
                         `----------------------------%0A` +
                         `👤 *Nama:* ${nama}%0A` +
                         `📱 *WhatsApp:* ${wa || '-'}%0A` +
                         `📦 *Item:* DRIP CLIENT FF%0A` +
                         `🕒 *Durasi:* ${currentAppVarian}%0A` +
                         `💰 *Total:* Rp ${currentAppHarga.toLocaleString('id-ID')}%0A` +
                         `----------------------------%0A` +
                         `_Mohon segera diproses Admin!_`;

            window.open(`https://wa.me/${admin}?text=${teks}`, '_blank');
        }

        window.onload = () => {
            if (localStorage.getItem('app-theme') === 'light') {
                document.documentElement.classList.remove('dark');
                document.getElementById('theme-icon').classList.replace('fa-moon', 'fa-sun');
            }
        };
    </script>
</body>
</html>

```
