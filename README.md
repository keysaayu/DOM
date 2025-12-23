# DOM
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    <!--onmouseover = ketika kursor didekatkan ke teks, teks jadi berbubah warna-->
    <h1 id="title" onmouseover="titleBaru()" onclick="titleBaru()">Selamat datang </h1>
    <h1 id="warna">Warna apa? </h1>

    <button onclick="ubah()">Klik sana</button>
    <button onclick="kembali()">Klik sini</button>

    <br><br>
    <label for="pilihWarna">Pilih warna background:</label>
    <input type="color" id="pilihWarna" oninput="pilihWarnaManual()">
    
    <br><br>
    <label for="colorInput">Pilih warna teks:</label>
    <input type="color" id="colorInput" oninput="pilihColor()">

    
    <script>
        const teksWarna = document.getElementById("warna");
        const teksTitle = document.getElementById("title");
        const daftarWarna = ["red", "purple", "magenta", "pink"];

        function titleBaru() {
            teksTitle.innerText = "Hello, gurll";
            const warnaAcak = daftarWarna[Math.floor(Math.random() * daftarWarna.length)];
            teksTitle.style.color = warnaAcak;
        }

        function ubah() {
            teksTitle.innerText = "Hello, gurll";
            
            const indexAcak = Math.floor(Math.random() * daftarWarna.length);
            const warnaTerpilih = daftarWarna[indexAcak];
            teksWarna.style.color = warnaTerpilih;
        }

        function kembali(){
            document.getElementById("title").innerText= "Selamat datangggg";
            teksTitle.style.color = "purple";
        }

        function pilihWarnaManual() {
            const warnaDipilih = document.getElementById("pilihWarna").value;
            document.body.style.backgroundColor = warnaDipilih;
            document.getElementById("warna").innerText = "Warna: " + warnaDipilih;
        }

        function pilihColor() {
            const warnaUser = document.getElementById("colorInput").value;
            document.getElementById("warna").style.color = warnaUser;
            document.getElementById("warna").innerText = "Warna Pilihan: " + warnaUser;
        }
        document.getElementById("warna").style.color= "pink";

        
    </script>
</body>
</html>
