<pDOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bazar Makanan Sekolah</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet"> <!-- Google Fonts -->
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background: url('https://source.unsplash.com/featured/?school-food') no-repeat center center fixed; /* Latar belakang gambar makanan sekolah dari Unsplash */
            background-size: cover;
            color: #333;
        }
        header {
            background-color: rgba(255, 165, 0, 0.9); /* Oranye transparan */
            color: white;
            text-align: center;
            padding: 20px;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.9); /* Putih transparan */
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .menu {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }
        .item {
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 10px;
            margin: 10px;
            padding: 15px;
            width: 300px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .item img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
        }
        button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
        #map {
            height: 300px;
            width: 100%;
            border-radius: 10px;
            margin-top: 20px;
        }
        #qr-section {
            text-align: center;
            margin-top: 20px;
        }
        #qrcode {
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Selamat Datang di Bazar Makanan Sekolah!</h1>
        <p>Makanan lezat dan sehat untuk siswa. Pesan sekarang!</p>
    </header>
    
    <div class="container">
        <h2>Menu Makanan</h2>
        <div class="menu">
            <div class="item">
                <a href="https://ibb.co.com/ns9ddvJD"><img src="https://i.ibb.co.com/bgTwwZ9r/IMG-20260212-WA0078.jpg" alt="IMG-20260212-WA0078" border="0"></a> </a> 
                <h3>Sticky Milk</h3>
                <p> Minuman segar dari susu pilihan,tidak mengandung pengawet dan pemanis buatan.</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
            <div class="item">
               <a href="https://ibb.co.com/j9vsVBnv"><img src="https://i.ibb.co.com/vCxRsg0x/IMG-20260212-WA0076.jpg" alt="IMG 20260212 WA0076" border="0"> </a>
                <h3> Es Jelly Pelangi</he>
                <p> Es Jelly yang isinya jelly warna-warni seperti warna pelangi(tanpa pemanis buatan!).</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
            <div class="item">
                <a href="https://ibb.co.com/Dfv15863"><img src="https://i.ibb.co.com/pjM1JRsC/IMG-20260212-WA0081.jpg" alt="IMG 20260212 WA0081" border="0">
                </a>
                <h3>Es Lumut Nutrijell</h3>
                <p>Es penyegar tenggorokan yang dibuat dari jelly Nutrijell dengan gula asli.</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
           
               
            <div class="item">
                 <a href="https://ibb.co.com/9mjfykYx"><img src="https://i.ibb.co.com/mr7YhVzn/IMG-20260212-WA0079.jpg" alt="IMG 20260212 WA0079" border="0"></a>              
                  <h3>Pisang Coklat (Piscok)</h3>
                <p>Pisang yang dibaluti oleh kulit lumpia dan berisi coklat.</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
              <div class="item">
                 <a href="https://ibb.co.com/5W5NxYGf"><img src="https://i.ibb.co.com/ccNGXbk7/IMG-20260212-WA0080.jpg" alt="IMG 20260212 WA0080" border="0"></a>         
                  <h3> Mie Eko </h3>
                <p> Camilan mie yang dibuat dengan sepenuh hati.</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
              <div class="item">
                 <a href="https://ibb.co.com/Wvh6PK4X"><img src="https://i.ibb.co.com/5h06ncg3/Screenshot-20260213-212041.jpg" alt="Screenshot 20260213 212041" border="0"></a>             
                  <h3>Salad SES</h3>
                <p>Jus jeruk atau mangga segar untuk penyegar.</p>
                <p><strong>Rp 5.000</strong></p>
                <button>Pesan</button>
            </div>
        </div>
        
        <h2>Lokasi Bazar</h2>
      <div> Koridor samping kelas 9B</div> 
        
        <div id="qr-section">
            <h2>Scan QR untuk Akses Cepat</h2>
            <button onclick="generateQR()">Generate QR Code</button>
            <div id="qrcode"></div>
        </div>
    </div>

    <script src=""></script> <!-- Library QR Code -->
    <script> 
      

        

        // Generate QR Code
        function generateQR() {
            const url = window.location.href; // URL website ini
            document.getElementById('qrcode').innerHTML = ''; // Clear previous QR
            new QRCode(document.getElementById('qrcode'), {
                text: url,
                width: 128,
                height: 128,
            });
        }
    </script>
</body>
</html>
