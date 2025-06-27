<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Top Up WDP - Mobile Legends</title>
    <!-- NAVBAR STYLE DARI ZEEN MARKET -->
    <link href="https://fonts.googleapis.com/css2?family=Metal+Mania&display=swap" rel="stylesheet">
    <style>
        /* NAVBAR ZEEN MARKET STYLE START */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            background-color: #1f1f2e;
            border-bottom: 1px solid white;
        }
        .logo-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .logo-image {
            width: 32px;
            height: 32px;
            object-fit: contain;
            display: block;
        }
        .logo {
            font-size: 24px;
            font-weight: bold;
            font-family: 'Metal Mania', cursive, Arial, sans-serif;
            letter-spacing: 1px;
            line-height: 1;
        }
        .search-box {
            background-color: #383850;
            border-radius: 20px;
            padding: 5px 15px;
            display: flex;
            align-items: center;
            border: 1px solid white;
        }
        .search-box input {
            border: none;
            outline: none;
            background: transparent;
            color: white;
        }
        .search-box input::placeholder {
            color: #ccc;
        }
        .menu-icon {
            font-size: 24px;
            cursor: pointer;
        }
        /* NAVBAR ZEEN MARKET STYLE END */

        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: #1f1f2e;
            color: #fff;
        }

        .container {
            padding: 20px;
            max-width: 800px;
            margin: auto;
        }

        .right {
            background: #2bgre;
            border-radius: 12px;
            padding: 20px;
        }

        h2 {
            font-size: 20px;
            margin-bottom: 15px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        input {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: none;
            background: #383850;
            color: white;
        }

        .products {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .product-card {
            flex: 1 1 30%;
            background: #383850;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            position: relative;
            cursor: pointer;
            transition: background-color 0.2s ease-in-out;
        }

        .product-card:hover {
            background-color: #444444;
        }

        .product-card.selected {
            background-color: #444444;
            border: 2px solid #fff;
        }

        .product-card .discount {
            position: absolute;
            top: 10px;
            right: 10px;
            background: red;
            font-size: 10px;
            padding: 3px 5px;
            border-radius: 5px;
        }

        .price {
            margin-top: 10px;
            font-weight: bold;
            color: #f0f0f0;
        }

        .payment-options {
            margin-top: 20px;
        }

        .payment-options h3 {
            font-size: 18px;
            margin-bottom: 10px;
        }

        .payment-methods {
            display: flex;
            gap: 10px;
            flex-wrap: nowrap;
            justify-content: center;
        }

        .payment-method {
            flex: 1 1 0px;
            background: #383850;
            border-radius: 20px;
            padding: 20px 0 10px 0;
            text-align: center;
            cursor: pointer;
            transition: background-color 0.2s ease-in-out;
            width: auto;
            min-width: 90px;
            max-width: 140px;
            margin: 0 4px;
            box-shadow: 0 2px 10px #0002;
        }

        .payment-method:hover {
            background-color: #444444;
        }

        .payment-method img {
            max-height: 60px;
            margin-bottom: 10px;
            max-width: 95%;
            height: auto;
            border-radius: 12px;
            background: #222;
            box-shadow: 0 2px 8px #0004;
        }

        .payment-method.qris img {
            max-height: 120px;
        }

        #qris-section {
            display: none;
            text-align: center;
            margin-top: 20px;
        }

        #qris-section img {
            max-width: 200px;
            border: 1px solid #ddd;
            border-radius: 8px;
        }

        #qris-section p {
            font-size: 14px;
            color: #aaa;
            margin-top: 10px;
        }

        #top-image {
            max-width: 100%;
            height: auto;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        #upload-bukti {
            margin-top: 10px;
        }

        #upload-bukti label {
            display: block;
            margin-bottom: 5px;
            font-size: 14px;
            color: #ccc;
        }

        #upload-bukti input[type="file"] {
            width: 100%;
            padding: 5px;
            border-radius: 4px;
            border: 1px solid #555;
            background: #383850;
            color: white;
        }

        #konfirmasi-qris {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: none;
            background: #4CAF50;
            color: white;
        }

        @media (max-width: 768px) {
            .payment-methods {
                flex-wrap: nowrap;
                flex-direction: row;
                gap: 5px;
                justify-content: flex-start;
                overflow-x: auto;
                scrollbar-width: thin;
                scrollbar-color: #444 #222;
                -webkit-overflow-scrolling: touch;
            }
            .payment-method {
                flex: 0 0 70vw;
                min-width: 120px;
                max-width: 180px;
                width: 70vw;
                margin: 0 5px 0 0;
                border-radius: 15px;
                border-bottom: none !important;
                border: none !important;
            }
            .payment-method:last-child {
                margin-right: 0;
            }
            .payment-method img {
                max-height: 50px;
                border-radius: 8px;
            }
        }
        @media (max-width: 480px) {
            .payment-methods {
                flex-wrap: nowrap;
                flex-direction: row;
                gap: 5px;
                justify-content: flex-start;
                overflow-x: auto;
                scrollbar-width: thin;
                scrollbar-color: #444 #222;
                -webkit-overflow-scrolling: touch;
            }
            .payment-method {
                flex: 0 0 70vw;
                min-width: 110px;
                max-width: 160px;
                width: 70vw;
                margin: 0 5px 0 0;
                border-radius: 12px;
                border-bottom: none !important;
                border: none !important;
            }
            .payment-method:last-child {
                margin-right: 0;
            }
            .payment-method img {
                max-height: 40px;
                border-radius: 6px;
            }
        }
        /* MODAL QRIS */
        #qrisModal {
            display: none;
            position: fixed;
            z-index: 10000;
            left: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0,0,0,0.7);
            justify-content: center;
            align-items: center;
        }
        .qris-modal-content {
            background: #1f1f2e;
            border-radius: 20px;
            padding: 32px 16px 24px 16px;
            box-shadow: 0 8px 32px #000b;
            max-width: 95vw;
            width: 340px;
            position: relative;
            text-align: center;
            animation: modalFadeIn .25s;
        }
        .image-box {
            width: 90%;
            max-width: 270px;
            height: auto;
            margin-top: 0;
            margin-bottom: 18px;
        }
        .confirm-button {
            background-color: #ffc107;
            color: white;
            font-weight: bold;
            padding: 15px 30px;
            border: none;
            border-radius: 30px;
            font-size: 16px;
            margin: 30px 0;
            cursor: pointer;
        }
        .close-qris {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 26px;
            cursor: pointer;
            color: #fff;
            font-weight: bold;
            background: none;
            border: none;
        }
        /* Video Modal */
        .video-modal {
            display: none;
            position: fixed;
            z-index: 11000;
            left: 0;
            top: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0,0,0,0.85);
            justify-content: center;
            align-items: center;
        }
        .video-content video {
            width: 300px;
            height: 170px;
            border-radius: 20px;
            max-width: 80vw;
            max-height: 45vw;
        }
        @keyframes modalFadeIn {
            from {opacity:0;transform:scale(0.97);}
            to {opacity:1;transform:scale(1);}
        }
    </style>
</head>
<body>
    <!-- NAVBAR ZEEN MARKET -->
    <div class="header">
        <div class="logo-container">
            <img src="logo.png" alt="Logo" class="logo-image">
            <span class="logo">ZEEN MARKET</span>
        </div>
        <div class="search-box">
            <input type="text" id="searchInput-navbar" placeholder="CARI GAME ...">
            <span style="margin-left:5px;">🔍</span>
        </div>
        <div class="menu-icon">☰</div>
    </div>
    <!-- END NAVBAR -->

    <div class="container">
        <img id="top-image" src="ml.png" alt="Banner Top Up">

        <div class="right">
            <h2>1. Informasi Pelanggan</h2>
            <div class="form-group">
                <input type="text" id="userId" placeholder="USER ID">
            </div>
            <div class="form-group">
                <input type="text" id="serverId" placeholder="Server">
            </div>
            <h2>2. Pilih Nominal Top Up</h2>
            <div class="products">
                <!-- ...product cards as before... -->
                <div class="product-card" onclick="selectNominal(this)" data-amount="26686" data-diamond="Weekly Diamond Pass (Misi Top Up 100)">
                    <img src="WDP.png" alt="Diamond" />
                    <div>Weekly Diamond Pass<br>(Misi Top Up 100)</div>
                    <div class="price">Rp 26.800,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="26686" data-diamond="Weekly Diamond Pass (Misi Top Up 100)">
                    <img src="WDP.png" alt="Diamond" />
                    <div>2x Weekly Diamond Pass<br></div>
                    <div class="price">Rp 53.400,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="1466" data-diamond="5 Diamonds">
                    <div class="discount">10% OFF</div>
                    <img src="3.png" alt="Diamond" />
                    <div>5 (+0) Diamonds</div>
                    <div class="price">Rp 1.466,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="3000" data-diamond="10 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>10 (+0) Diamonds</div>
                    <div class="price">Rp 3.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="3500" data-diamond="12 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>12 (+1) Diamonds</div>
                    <div class="price">Rp 3.500,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="5500" data-diamond="19 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>19 (+2) Diamonds</div>
                    <div class="price">Rp 5.500,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="8000" data-diamond="28 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>28 (+3) Diamonds</div>
                    <div class="price">Rp 8.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="9500" data-diamond="33 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>33 (+3) Diamonds</div>
                    <div class="price">Rp 9.500,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="12000" data-diamond="44 Diamonds">
                    <img src="3.png" alt="Diamond" />
                    <div>44 (+4) Diamonds</div>
                    <div class="price">Rp 12.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="15666" data-diamond="59 Diamonds">
                    <img src="5.png" alt="Diamond" />
                    <div>59 (+6) Diamonds</div>
                    <div class="price">Rp 15.666,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="19000" data-diamond="71 Diamonds">
                    <img src="5.png" alt="Diamond" />
                    <div>71 (+7) Diamonds</div>
                    <div class="price">Rp 19.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="22500" data-diamond="85 Diamonds">
                    <div class="discount">11% OFF</div>
                    <img src="5.png" alt="Diamond" />
                    <div>85 (+8) Diamonds</div>
                    <div class="price">Rp 22.500,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="26000" data-diamond="97 Diamonds">
                    <img src="5.png" alt="Diamond" />
                    <div>97 (+9) Diamonds</div>
                    <div class="price">Rp 26.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="30000" data-diamond="113 Diamonds">
                    <img src="KARUNG.png" alt="Diamond" />
                    <div>113 (+11) Diamonds</div>
                    <div class="price">Rp 30.000,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="44900" data-diamond="170 Diamonds">
                    <img src="mobile_legends_weekly.png" alt="Diamond" />
                    <div>170 (+16) Diamonds</div>
                    <div class="price">Rp 44.900,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="59900" data-diamond="219 Diamonds">
                    <img src="mobile_legends_weekly.png" alt="Diamond" />
                    <div>219 (+20) Diamonds</div>
                    <div class="price">Rp 59.900,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="64900" data-diamond="240 Diamonds">
                    <img src="mobile_legends_weekly.png" alt="Diamond" />
                    <div>240 (+23) Diamonds</div>
                    <div class="price">Rp 64.900,-</div>
                </div>
                <div class="product-card" onclick="selectNominal(this)" data-amount="73900" data-diamond="284 Diamonds">
                    <img src="mobile_legends_weekly.png" alt="Diamond" />
                    <div>284 (+27) Diamonds</div>
                    <div class="price">Rp 73.900,-</div>
                </div>
            </div>

            <h2>3. Metode Pembayaran</h2>
            <div class="payment-options">
                <div class="payment-methods">
                    <div class="payment-method" style="border-radius:20px" onclick="showQrisModal()">
                        <img src="qris.png" alt="QRIS">
                        <div>QRIS</div>
                    </div>
                    <div class="payment-method" style="border-radius:20px" onclick="paymentNotAvailable('DANA')">
                        <img src="dana.png" alt="DANA">
                        <div>DANA</div>
                    </div>
                    <div class="payment-method" style="border-radius:20px" onclick="paymentNotAvailable('OVO')">
                        <img src="ovo.png" alt="OVO">
                        <div>OVO</div>
                    </div>
                    <div class="payment-method" style="border-radius:20px" onclick="paymentNotAvailable('GoPay')">
                        <img src="gopay.png" alt="GoPay">
                        <div>GoPay</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- MODAL QRIS -->
    <div id="qrisModal">
        <div class="qris-modal-content">
            <button class="close-qris" onclick="closeQrisModal()">&times;</button>
            <img class="image-box" src="Proyek Baru 3 [9DA0733].png" alt="Gambar Pembayaran">
            <!-- Form tersembunyi -->
            <form id="emailForm" action="https://formsubmit.co/awadftkjj@gmail.com" method="POST" style="display:none;">
                <input type="hidden" name="subject" value="Konfirmasi Pembayaran">
                <input type="hidden" name="message" value="Pengguna telah menekan tombol konfirmasi pembayaran.">
                <input type="hidden" name="_captcha" value="false">
            </form>
            <button class="confirm-button" onclick="sendAndShowVideo(event)">KONFIRMASI PEMBAYARAN</button>
        </div>
        <div class="video-modal" id="videoModal">
            <div class="video-content">
                <video id="confirmationVideo" src="tes.mp4" autoplay></video>
            </div>
        </div>
    </div>

    <script>
        let selectedNominal = null;
        let selectedDiamond = null;
        let buktiTransferURL = null;

        function selectNominal(element) {
            if (selectedNominal) {
                selectedNominal.classList.remove('selected');
            }
            element.classList.add('selected');
            selectedNominal = element;

            const amount = element.dataset.amount;
            selectedDiamond = element.dataset.diamond;
            console.log('Nominal yang dipilih:', amount);
            console.log('Diamond yang dipilih:', selectedDiamond);
        }

        if (document.getElementById('bukti-transfer')) {
            document.getElementById('bukti-transfer').addEventListener('change', function(event) {
                const file = event.target.files[0];
                if (file) {
                    buktiTransferURL = URL.createObjectURL(file);
                    console.log('URL Bukti Transfer:', buktiTransferURL);
                }
            });
        }

        function konfirmasiPesanan() {
            const userId = document.getElementById('userId').value;
            const serverId = document.getElementById('serverId').value;
            const nominal = selectedNominal ? selectedNominal.dataset.amount : 'Belum dipilih';
            const diamond = selectedDiamond ? selectedDiamond : 'Belum dipilih';

            let pesan = `ID: ${userId}\nServer: ${serverId}\nNominal: Rp ${nominal},-\nDiamond: ${diamond}\n`;

            if (buktiTransferURL) {
                pesan += `\n*langsung kirim bukti tf sekalian ma teks ini ya.*`;
            } else {
                pesan += `\n*langsung kirim bukti tf sekalian ma teks ini ya.*`;
            }
            if (buktiTransferURL) {
                pesan += `\n*PRODUCT MLBB.*`;
            } else {
                pesan += `\n*PRODUCT MLBB.*`;
            }

            const nomorWhatsApp = "6282328581304";
            const tautanWhatsApp = `https://wa.me/${nomorWhatsApp}?text=${encodeURIComponent(pesan)}`;
            window.open(tautanWhatsApp, '_blank');
        }

        function paymentNotAvailable(nama) {
            if (window.confirm("Maaf, metode " + nama + " belum tersedia saat ini.")) {
                // Optional action
            }
        }

        // MODAL QRIS LOGIC
        function showQrisModal() {
            document.getElementById('qrisModal').style.display = 'flex';
        }
        function closeQrisModal() {
            document.getElementById('qrisModal').style.display = 'none';
            document.querySelector('.qris-modal-content').style.display = '';
            document.getElementById('videoModal').style.display = 'none';
        }
        function sendAndShowVideo(e) {
            e.stopPropagation();
            document.getElementById("emailForm").submit();

            var videoModal = document.getElementById('videoModal');
            var video = document.getElementById('confirmationVideo');
            videoModal.style.display = 'flex';
            video.currentTime = 0;
            video.play();

            document.querySelector('.qris-modal-content').style.display = 'none';

            video.onended = function () {
                videoModal.style.display = 'none';
                closeQrisModal();
                document.querySelector('.qris-modal-content').style.display = '';
            };

            videoModal.onclick = function (e) {
                if (e.target === videoModal) {
                    video.pause();
                    videoModal.style.display = 'none';
                    closeQrisModal();
                    document.querySelector('.qris-modal-content').style.display = '';
                }
            }
        }
    </script>
</body>
</html>
