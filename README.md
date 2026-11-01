<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Bio Solar</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        /* Custom scrollbar for a cleaner look */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1; 
        }
        ::-webkit-scrollbar-thumb {
            background: #888; 
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #555; 
        }
    </style>
</head>
<body class="bg-emerald-50 min-h-screen flex items-center justify-center p-4">

    <div class="max-w-md w-full bg-white rounded-3xl shadow-xl overflow-hidden border border-emerald-100">
        
        <!-- Header Section -->
        <div class="bg-gradient-to-br from-emerald-500 to-green-600 p-6 text-white text-center relative overflow-hidden">
            <!-- Decorative circle -->
            <div class="absolute -top-10 -right-10 w-32 h-32 bg-white opacity-10 rounded-full blur-2xl"></div>
            
            <div class="flex justify-center mb-3">
                <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="text-emerald-100">
                    <path d="M11 20A7 7 0 0 1 9.8 6.1C15.5 5 17 4.48 19 2c1 2 2 4.18 2 8 0 5.5-4.78 10-10 10Z"/>
                    <path d="M2 21c0-3 1.85-5.36 5.08-6C9.5 14.52 12 13 13 12"/>
                </svg>
            </div>
            <h1 class="text-2xl font-bold tracking-tight">Kalkulator Bio Solar</h1>
            <p class="text-emerald-100 text-sm mt-1 opacity-90">Hitung estimasi kebutuhan & biaya perjalanan Anda</p>
        </div>

        <!-- Input Section -->
        <div class="p-6 space-y-5">
            
            <!-- Jarak Tempuh -->
            <div>
                <label for="jarak" class="block text-sm font-semibold text-gray-700 mb-1">Jarak Tempuh (km)</label>
                <div class="relative">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6" />
                        </svg>
                    </div>
                    <input type="number" id="jarak" placeholder="Contoh: 150" min="0" step="any"
                        class="w-full pl-10 pr-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 transition-all text-gray-800 placeholder-gray-400">
                </div>
            </div>

            <!-- Konsumsi BBM -->
            <div>
                <label for="konsumsi" class="block text-sm font-semibold text-gray-700 mb-1">Konsumsi BBM (km/liter)</label>
                <div class="relative">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 6l3 1m0 0l-3 9a5.002 5.002 0 006.001 0M6 7l3 9M6 7l6-2m6 2l3-1m-3 1l-3 9a5.002 5.002 0 006.001 0M18 7l3 9m-3-9l-6-2m0-2v2m0 16V5m0 16H9m3 0h3" />
                        </svg>
                    </div>
                    <input type="number" id="konsumsi" placeholder="Contoh: 12" min="0" step="any"
                        class="w-full pl-10 pr-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 transition-all text-gray-800 placeholder-gray-400">
                </div>
                <p class="text-xs text-gray-500 mt-1">Rata-rata penggunaan kendaraan Anda.</p>
            </div>

            <!-- Harga Bio Solar -->
            <div>
                <label for="harga" class="block text-sm font-semibold text-gray-700 mb-1">Harga Bio Solar (Rp/liter)</label>
                <div class="relative">
                    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
                        <span class="text-gray-400 font-medium">Rp</span>
                    </div>
                    <input type="number" id="harga" value="6800" min="0" step="any"
                        class="w-full pl-10 pr-4 py-3 bg-gray-50 border border-gray-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 transition-all text-gray-800">
                </div>
            </div>

            <!-- Divider -->
            <hr class="border-gray-100 my-4">

            <!-- Result Section -->
            <div class="bg-emerald-50 rounded-2xl p-5 border border-emerald-100">
                <h3 class="text-sm font-semibold text-emerald-800 mb-4 uppercase tracking-wider">Estimasi Perjalanan</h3>
                
                <div class="flex justify-between items-end mb-3">
                    <span class="text-gray-600 font-medium text-sm">BBM Dibutuhkan</span>
                    <span id="hasilLiter" class="text-xl font-bold text-emerald-700">0.00 L</span>
                </div>
                
                <div class="flex justify-between items-end">
                    <span class="text-gray-600 font-medium text-sm">Total Biaya</span>
                    <span id="hasilBiaya" class="text-2xl font-black text-emerald-600">Rp 0</span>
                </div>
            </div>

        </div>
        
        <!-- Footer -->
        <div class="bg-gray-50 p-4 text-center text-xs text-gray-500 border-t border-gray-100">
            <p>♻️ Mendukung penggunaan energi yang lebih ramah lingkungan.</p>
        </div>

    </div>

    <script>
        // Ambil elemen input dan output
        const inputJarak = document.getElementById('jarak');
        const inputKonsumsi = document.getElementById('konsumsi');
        const inputHarga = document.getElementById('harga');
        const outputLiter = document.getElementById('hasilLiter');
        const outputBiaya = document.getElementById('hasilBiaya');

        // Fungsi format Rupiah
        const formatRupiah = (number) => {
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0,
                maximumFractionDigits: 0
            }).format(number);
        };

        // Fungsi Kalkulasi
        function hitungBioSolar() {
            const jarak = parseFloat(inputJarak.value) || 0;
            const konsumsi = parseFloat(inputKonsumsi.value) || 0;
            const harga = parseFloat(inputHarga.value) || 0;

            let totalLiter = 0;
            let totalBiaya = 0;

            // Hindari pembagian dengan nol
            if (konsumsi > 0 && jarak > 0) {
                totalLiter = jarak / konsumsi;
                totalBiaya = totalLiter * harga;
            }

            // Tampilkan hasil
            outputLiter.textContent = totalLiter.toFixed(2) + ' L';
            outputBiaya.textContent = formatRupiah(totalBiaya);
        }

        // Tambahkan event listener agar hasil terupdate otomatis saat mengetik
        inputJarak.addEventListener('input', hitungBioSolar);
        inputKonsumsi.addEventListener('input', hitungBioSolar);
        inputHarga.addEventListener('input', hitungBioSolar);

        // Jalankan sekali saat load untuk menginisialisasi angka nol
        hitungBioSolar();
    </script>
</body>
</html>