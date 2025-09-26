<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pendaftaran Siswa Baru - SMKN 1 Purbalingga</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .step-indicator {
            transition: all 0.3s ease;
        }
        .step-indicator.active {
            background-color: #3b82f6;
            color: white;
        }
        .step-indicator.completed {
            background-color: #10b981;
            color: white;
        }
        .form-section {
            display: none;
        }
        .form-section.active {
            display: block;
            animation: fadeIn 0.3s ease-in;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .preview-item {
            transition: all 0.2s ease;
        }
        .preview-item:hover {
            background-color: #f3f4f6;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="bg-blue-600 text-white shadow-lg">
        <div class="container mx-auto px-4 py-6">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-4">
                    <i class="fas fa-school text-3xl"></i>
                    <div>
                        <h1 class="text-2xl font-bold">SMKN 1 Purbalingga</h1>
                        <p class="text-blue-100">Sistem Pendaftaran Siswa Baru Tahun Ajaran 2024/2025</p>
                    </div>
                </div>
                <div class="text-right">
                    <p class="text-sm text-blue-100">PPDB Online</p>
                    <p class="text-lg font-semibold" id="currentTime"></p>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
        <!-- Progress Steps -->
        <div class="bg-white rounded-lg shadow-md p-6 mb-8">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-4">
                    <div class="step-indicator active w-10 h-10 rounded-full flex items-center justify-center font-semibold" data-step="1">1</div>
                    <span class="text-sm font-medium">Data Diri</span>
                </div>
                <div class="flex-1 h-1 bg-gray-300 mx-4"></div>
                <div class="flex items-center space-x-4">
                    <div class="step-indicator w-10 h-10 rounded-full flex items-center justify-center font-semibold bg-gray-300" data-step="2">2</div>
                    <span class="text-sm font-medium">Data Orang Tua</span>
                </div>
                <div class="flex-1 h-1 bg-gray-300 mx-4"></div>
                <div class="flex items-center space-x-4">
                    <div class="step-indicator w-10 h-10 rounded-full flex items-center justify-center font-semibold bg-gray-300" data-step="3">3</div>
                    <span class="text-sm font-medium">Data Akademik</span>
                </div>
                <div class="flex-1 h-1 bg-gray-300 mx-4"></div>
                <div class="flex items-center space-x-4">
                    <div class="step-indicator w-10 h-10 rounded-full flex items-center justify-center font-semibold bg-gray-300" data-step="4">4</div>
                    <span class="text-sm font-medium">Konfirmasi</span>
                </div>
            </div>
        </div>

        <!-- Form Container -->
        <div class="bg-white rounded-lg shadow-md p-8">
            <form id="registrationForm">
                <!-- Step 1: Data Diri -->
                <div class="form-section active" id="step1">
                    <h2 class="text-2xl font-bold mb-6 text-gray-800">
                        <i class="fas fa-user mr-2 text-blue-600"></i>Data Diri Siswa
                    </h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Nama Lengkap <span class="text-red-500">*</span></label>
                            <input type="text" name="namaLengkap" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">NISN <span class="text-red-500">*</span></label>
                            <input type="text" name="nisn" required pattern="[0-9]{10}" maxlength="10" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Tempat Lahir <span class="text-red-500">*</span></label>
                            <input type="text" name="tempatLahir" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Tanggal Lahir <span class="text-red-500">*</span></label>
                            <input type="date" name="tanggalLahir" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Jenis Kelamin <span class="text-red-500">*</span></label>
                            <select name="jenisKelamin" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <option value="">Pilih Jenis Kelamin</option>
                                <option value="L">Laki-laki</option>
                                <option value="P">Perempuan</option>
                            </select>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Agama <span class="text-red-500">*</span></label>
                            <select name="agama" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <option value="">Pilih Agama</option>
                                <option value="Islam">Islam</option>
                                <option value="Kristen">Kristen</option>
                                <option value="Katolik">Katolik</option>
                                <option value="Hindu">Hindu</option>
                                <option value="Buddha">Buddha</option>
                                <option value="Konghucu">Konghucu</option>
                            </select>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">No. HP <span class="text-red-500">*</span></label>
                            <input type="tel" name="noHp" required pattern="[0-9]{10,13}" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Email <span class="text-red-500">*</span></label>
                            <input type="email" name="email" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                    </div>
                    
                    <div class="mt-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Alamat Lengkap <span class="text-red-500">*</span></label>
                        <textarea name="alamat" required rows="3" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"></textarea>
                    </div>
                    
                    <div class="flex justify-end mt-8">
                        <button type="button" onclick="nextStep(2)" class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition duration-200">
                            Lanjut <i class="fas fa-arrow-right ml-2"></i>
                        </button>
                    </div>
                </div>

                <!-- Step 2: Data Orang Tua -->
                <div class="form-section" id="step2">
                    <h2 class="text-2xl font-bold mb-6 text-gray-800">
                        <i class="fas fa-users mr-2 text-blue-600"></i>Data Orang Tua/Wali
                    </h2>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold mb-4 text-gray-700">Data Ayah</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Nama Ayah <span class="text-red-500">*</span></label>
                                <input type="text" name="namaAyah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Pekerjaan Ayah <span class="text-red-500">*</span></label>
                                <input type="text" name="pekerjaanAyah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Pendidikan Ayah <span class="text-red-500">*</span></label>
                                <select name="pendidikanAyah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                    <option value="">Pilih Pendidikan</option>
                                    <option value="SD">SD</option>
                                    <option value="SMP">SMP</option>
                                    <option value="SMA">SMA</option>
                                    <option value="D3">D3</option>
                                    <option value="S1">S1</option>
                                    <option value="S2">S2</option>
                                    <option value="S3">S3</option>
                                </select>
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">No. HP Ayah</label>
                                <input type="tel" name="noHpAyah" pattern="[0-9]{10,13}" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                        </div>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold mb-4 text-gray-700">Data Ibu</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Nama Ibu <span class="text-red-500">*</span></label>
                                <input type="text" name="namaIbu" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Pekerjaan Ibu <span class="text-red-500">*</span></label>
                                <input type="text" name="pekerjaanIbu" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Pendidikan Ibu <span class="text-red-500">*</span></label>
                                <select name="pendidikanIbu" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                    <option value="">Pilih Pendidikan</option>
                                    <option value="SD">SD</option>
                                    <option value="SMP">SMP</option>
                                    <option value="SMA">SMA</option>
                                    <option value="D3">D3</option>
                                    <option value="S1">S1</option>
                                    <option value="S2">S2</option>
                                    <option value="S3">S3</option>
                                </select>
                            </div>
                            
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">No. HP Ibu</label>
                                <input type="tel" name="noHpIbu" pattern="[0-9]{10,13}" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                            </div>
                        </div>
                    </div>
                    
                    <div class="flex justify-between mt-8">
                        <button type="button" onclick="prevStep(1)" class="bg-gray-500 text-white px-6 py-2 rounded-lg hover:bg-gray-600 transition duration-200">
                            <i class="fas fa-arrow-left mr-2"></i> Kembali
                        </button>
                        <button type="button" onclick="nextStep(3)" class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition duration-200">
                            Lanjut <i class="fas fa-arrow-right ml-2"></i>
                        </button>
                    </div>
                </div>

                <!-- Step 3: Data Akademik -->
                <div class="form-section" id="step3">
                    <h2 class="text-2xl font-bold mb-6 text-gray-800">
                        <i class="fas fa-graduation-cap mr-2 text-blue-600"></i>Data Akademik
                    </h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Asal Sekolah <span class="text-red-500">*</span></label>
                            <input type="text" name="asalSekolah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Alamat Sekolah <span class="text-red-500">*</span></label>
                            <input type="text" name="alamatSekolah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Tahun Lulus <span class="text-red-500">*</span></label>
                            <select name="tahunLulus" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <option value="">Pilih Tahun</option>
                                <option value="2024">2024</option>
                                <option value="2023">2023</option>
                                <option value="2022">2022</option>
                                <option value="2021">2021</option>
                            </select>
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">No. Ijazah/SKL <span class="text-red-500">*</span></label>
                            <input type="text" name="noIjazah" required class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Nilai UN Bahasa Indonesia <span class="text-red-500">*</span></label>
                            <input type="number" name="nilaiBindo" required min="0" max="100" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Nilai UN Matematika <span class="text-red-500">*</span></label>
                            <input type="number" name="nilaiMat" required min="0" max="100" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Nilai UN Bahasa Inggris <span class="text-red-500">*</span></label>
                            <input type="number" name="nilaiBing" required min="0" max="100" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                        
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Nilai UN IPA <span class="text-red-500">*</span></label>
                            <input type="number" name="nilaiIPA" required min="0" max="100" class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                        </div>
                    </div>
                    
                    <div class="mt-6">
                        <label class="block text-sm font-medium text-gray-700 mb-2">Pilihan Jurusan <span class="text-red-500">*</span></label>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="TKJ" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Teknik Komputer dan Jaringan</p>
                                    <p class="text-sm text-gray-600">Kuota: 120 siswa</p>
                                </div>
                            </label>
                            
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="RPL" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Rekayasa Perangkat Lunak</p>
                                    <p class="text-sm text-gray-600">Kuota: 120 siswa</p>
                                </div>
                            </label>
                            
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="MM" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Multimedia</p>
                                    <p class="text-sm text-gray-600">Kuota: 80 siswa</p>
                                </div>
                            </label>
                            
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="OTKP" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Otomatisasi dan Tata Kelola Perkantoran</p>
                                    <p class="text-sm text-gray-600">Kuota: 80 siswa</p>
                                </div>
                            </label>
                            
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="AKL" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Akuntansi dan Keuangan Lembaga</p>
                                    <p class="text-sm text-gray-600">Kuota: 80 siswa</p>
                                </div>
                            </label>
                            
                            <label class="flex items-center p-4 border border-gray-300 rounded-lg cursor-pointer hover:bg-blue-50">
                                <input type="radio" name="jurusan" value="BDP" required class="mr-3">
                                <div>
                                    <p class="font-semibold">Bisnis Daring dan Pemasaran</p>
                                    <p class="text-sm text-gray-600">Kuota: 80 siswa</p>
                                </div>
                            </label>
                        </div>
                    </div>
                    
                    <div class="flex justify-between mt-8">
                        <button type="button" onclick="prevStep(2)" class="bg-gray-500 text-white px-6 py-2 rounded-lg hover:bg-gray-600 transition duration-200">
                            <i class="fas fa-arrow-left mr-2"></i> Kembali
                        </button>
                        <button type="button" onclick="nextStep(4)" class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition duration-200">
                            Lanjut <i class="fas fa-arrow-right ml-2"></i>
                        </button>
                    </div>
                </div>

                <!-- Step 4: Konfirmasi -->
                <div class="form-section" id="step4">
                    <h2 class="text-2xl font-bold mb-6 text-gray-800">
                        <i class="fas fa-check-circle mr-2 text-blue-600"></i>Konfirmasi Data
                    </h2>
                    
                    <div class="bg-blue-50 border border-blue-200 rounded-lg p-4 mb-6">
                        <p class="text-blue-800"><i class="fas fa-info-circle mr-2"></i>Silakan periksa kembali data yang Anda masukkan sebelum mengirimkan pendaftaran.</p>
                    </div>
                    
                    <div id="previewData" class="space-y-6">
                        <!-- Preview data akan diisi oleh JavaScript -->
                    </div>
                    
                    <div class="mt-6">
                        <label class="flex items-center">
                            <input type="checkbox" id="agreeTerms" required class="mr-2">
                            <span class="text-sm text-gray-700">Saya menyatakan bahwa data yang saya masukkan adalah benar dan dapat dipertanggungjawabkan.</span>
                        </label>
                    </div>
                    
                    <div class="flex justify-between mt-8">
                        <button type="button" onclick="prevStep(3)" class="bg-gray-500 text-white px-6 py-2 rounded-lg hover:bg-gray-600 transition duration-200">
                            <i class="fas fa-arrow-left mr-2"></i> Kembali
                        </button>
                        <button type="submit" class="bg-green-600 text-white px-6 py-2 rounded-lg hover:bg-green-700 transition duration-200">
                            <i class="fas fa-paper-plane mr-2"></i> Kirim Pendaftaran
                        </button>
                    </div>
                </div>
            </form>
        </div>
    </main>

    <!-- Success Modal -->
    <div id="successModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
        <div class="bg-white rounded-lg p-8 max-w-md w-full mx-4 transform transition-all">
            <div class="text-center">
                <div class="mx-auto flex items-center justify-center h-16 w-16 rounded-full bg-green-100 mb-4">
                    <i class="fas fa-check text-green-600 text-2xl"></i>
                </div>
                <h3 class="text-xl font-bold text-gray-900 mb-2">Pendaftaran Berhasil!</h3>
                <p class="text-gray-600 mb-6">Data pendaftaran Anda telah berhasil dikirim. Nomor pendaftaran Anda adalah:</p>
                <div class="bg-gray-100 rounded-lg p-4 mb-6">
                    <p class="text-2xl font-bold text-blue-600" id="registrationNumber">SMK1-2024-XXXX</p>
                </div>
                <p class="text-sm text-gray-500 mb-6">Silakan simpan nomor pendaftaran ini untuk keperluan selanjutnya.</p>
                <button onclick="closeModal()" class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition duration-200">
                    Tutup
                </button>
            </div>
        </div>
    </div>

    <script>
        // Update current time
        function updateTime() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric', hour: '2-digit', minute: '2-digit' };
            document.getElementById('currentTime').textContent = now.toLocaleDateString('id-ID', options);
        }
        updateTime();
        setInterval(updateTime, 60000);

        // Step navigation
        let currentStep = 1;

        function showStep(step) {
            document.querySelectorAll('.form-section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(`step${step}`).classList.add('active');
            
            document.querySelectorAll('.step-indicator').forEach((indicator, index) => {
                if (index + 1 < step) {
                    indicator.classList.add('completed');
                    indicator.classList.remove('active');
                } else if (index + 1 === step) {
                    indicator.classList.add('active');
                    indicator.classList.remove('completed');
                } else {
                    indicator.classList.remove('active', 'completed');
                }
            });
        }

        function nextStep(step) {
            if (validateCurrentStep()) {
                currentStep = step;
                showStep(step);
                if (step === 4) {
                    generatePreview();
                }
            }
        }

        function prevStep(step) {
            currentStep = step;
            showStep(step);
        }

        function validateCurrentStep() {
            const currentForm = document.getElementById(`step${currentStep}`);
            const inputs = currentForm.querySelectorAll('input[required], select[required], textarea[required]');
            let isValid = true;

            inputs.forEach(input => {
                if (!input.value) {
                    input.classList.add('border-red-500');
                    isValid = false;
                } else {
                    input.classList.remove('border-red-500');
                }
            });

            if (!isValid) {
                alert('Harap lengkapi semua field yang wajib diisi!');
            }

            return isValid;
        }

        function generatePreview() {
            const formData = new FormData(document.getElementById('registrationForm'));
            const previewData = document.getElementById('previewData');
            
            let html = '';
            
            // Data Diri
            html += `
                <div class="bg-gray-50 rounded-lg p-6">
                    <h3 class="text-lg font-semibold mb-4 text-gray-800">Data Diri</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Nama Lengkap</p>
                            <p class="font-medium">${formData.get('namaLengkap')}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">NISN</p>
                            <p class="font-medium">${formData.get('nisn')}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Tempat, Tanggal Lahir</p>
                            <p class="font-medium">${formData.get('tempatLahir')}, ${formatDate(formData.get('tanggalLahir'))}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Jenis Kelamin</p>
                            <p class="font-medium">${formData.get('jenisKelamin') === 'L' ? 'Laki-laki' : 'Perempuan'}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Agama</p>
                            <p class="font-medium">${formData.get('agama')}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">No. HP</p>
                            <p class="font-medium">${formData.get('noHp')}</p>
                        </div>
                        <div class="preview-item p-3 rounded md:col-span-2">
                            <p class="text-sm text-gray-600">Alamat</p>
                            <p class="font-medium">${formData.get('alamat')}</p>
                        </div>
                    </div>
                </div>
            `;
            
            // Data Orang Tua
            html += `
                <div class="bg-gray-50 rounded-lg p-6">
                    <h3 class="text-lg font-semibold mb-4 text-gray-800">Data Orang Tua</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div>
                            <h4 class="font-medium mb-2">Ayah</h4>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Nama</p>
                                <p class="font-medium">${formData.get('namaAyah')}</p>
                            </div>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Pekerjaan</p>
                                <p class="font-medium">${formData.get('pekerjaanAyah')}</p>
                            </div>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Pendidikan</p>
                                <p class="font-medium">${formData.get('pendidikanAyah')}</p>
                            </div>
                        </div>
                        <div>
                            <h4 class="font-medium mb-2">Ibu</h4>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Nama</p>
                                <p class="font-medium">${formData.get('namaIbu')}</p>
                            </div>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Pekerjaan</p>
                                <p class="font-medium">${formData.get('pekerjaanIbu')}</p>
                            </div>
                            <div class="preview-item p-3 rounded">
                                <p class="text-sm text-gray-600">Pendidikan</p>
                                <p class="font-medium">${formData.get('pendidikanIbu')}</p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
            
            // Data Akademik
            html += `
                <div class="bg-gray-50 rounded-lg p-6">
                    <h3 class="text-lg font-semibold mb-4 text-gray-800">Data Akademik</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Asal Sekolah</p>
                            <p class="font-medium">${formData.get('asalSekolah')}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Tahun Lulus</p>
                            <p class="font-medium">${formData.get('tahunLulus')}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Nilai Rata-rata UN</p>
                            <p class="font-medium">${calculateAverage()}</p>
                        </div>
                        <div class="preview-item p-3 rounded">
                            <p class="text-sm text-gray-600">Pilihan Jurusan</p>
                            <p class="font-medium">${getJurusanName(formData.get('jurusan'))}</p>
                        </div>
                    </div>
                </div>
            `;
            
            previewData.innerHTML = html;
        }

        function formatDate(dateString) {
            const date = new Date(dateString);
            const options = { day: 'numeric', month: 'long', year: 'numeric' };
            return date.toLocaleDateString('id-ID', options);
        }

        function calculateAverage() {
            const bindo = parseFloat(document.querySelector('input[name="nilaiBindo"]').value) || 0;
            const mat = parseFloat(document.querySelector('input[name="nilaiMat"]').value) || 0;
            const bing = parseFloat(document.querySelector('input[name="nilaiBing"]').value) || 0;
            const ipa = parseFloat(document.querySelector('input[name="nilaiIPA"]').value) || 0;
            
            const average = (bindo + mat + bing + ipa) / 4;
            return average.toFixed(2);
        }

        function getJurusanName(code) {
            const jurusan = {
                'TKJ': 'Teknik Komputer dan Jaringan',
                'RPL': 'Rekayasa Perangkat Lunak',
                'MM': 'Multimedia',
                'OTKP': 'Otomatisasi dan Tata Kelola Perkantoran',
                'AKL': 'Akuntansi dan Keuangan Lembaga',
                'BDP': 'Bisnis Daring dan Pemasaran'
            };
            return jurusan[code] || code;
        }

        // Form submission
        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            if (!document.getElementById('agreeTerms').checked) {
                alert('Harap centang pernyataan kebenaran data!');
                return;
            }
            
            // Generate registration number
            const randomNum = Math.floor(1000 + Math.random() * 9000);
            document.getElementById('registrationNumber').textContent = `SMK1-2024-${randomNum}`;
            
            // Show success modal
            document.getElementById('successModal').classList.remove('hidden');
        });

        function closeModal() {
            document.getElementById('successModal').classList.add('hidden');
            // Reset form
            document.getElementById('registrationForm').reset();
            currentStep = 1;
            showStep(1);
        }

        // Add input event listeners for real-time validation
        document.querySelectorAll('input, select, textarea').forEach(input => {
            input.addEventListener('input', function() {
                if (this.hasAttribute('required') && this.value) {
                    this.classList.remove('border-red-500');
                }
            });
        });
    </script>
</body>
</html>
