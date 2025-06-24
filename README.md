
<html lang="id">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pemesanan Pupuk Organik</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #e8f5e9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        
        .container {
            background: white;
            padding: 25px 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 420px;
        }
        
        h2 {
            text-align: center;
            color: #2e7d32;
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-top: 10px;
            font-weight: bold;
            color: #555;
        }
        
        input,
        select,
        textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 6px;
            border: 1px solid #ccc;
            box-sizing: border-box;
        }
        
        button {
            background-color: #43a047;
            color: white;
            border: none;
            padding: 14px;
            border-radius: 8px;
            font-size: 16px;
            margin-top: 20px;
            width: 100%;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #388e3c;
        }
    </style>
</head>

<body>

    <div class="container">
        <h2>Formulir Pemesanan Pupuk</h2>
        <form id="orderForm">
            <label for="nama">Nama</label>
            <input type="text" id="nama" name="nama" required>

            <label for="alamat">Alamat</label>
            <textarea id="alamat" name="alamat" rows="2" required></textarea>

            <label for="produk">Jenis Pupuk</label>
            <select id="produk" name="produk" required>
                <option value="Pupuk Organik">Pupuk Organik</option>
            </select>

            <label for="jumlah">Jumlah (karung)</label>
            <input type="number" id="jumlah" name="jumlah" required>

            <label for="kontak">Nomor Kontak</label>
            <input type="text" id="kontak" name="kontak" required>

            <button type="submit">Kirim via WhatsApp</button>
        </form>
    </div>

    <script>
        document.getElementById("orderForm").addEventListener("submit", function(e) {
            e.preventDefault();

            const nama = document.getElementById("nama").value;
            const alamat = document.getElementById("alamat").value;
            const produk = document.getElementById("produk").value;
            const jumlah = document.getElementById("jumlah").value;
            const kontak = document.getElementById("kontak").value;

            const adminPhone = "62881080293621"; // Ganti dengan nomor WhatsApp admin

            const pesan = `Halo Admin, saya ingin memesan pupuk:\n\nNama: ${nama}\nAlamat: ${alamat}\nProduk: ${produk}\nJumlah: ${jumlah} karung\nKontak: ${kontak}`;

            const url = `https://wa.me/${adminPhone}?text=${encodeURIComponent(pesan)}`;

            window.open(url, '_blank');
        });
    </script>

</body>

</html>
