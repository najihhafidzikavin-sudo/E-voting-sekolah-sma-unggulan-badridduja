# htpps://E-voting-sekolah-sma-unggulan-badridduja//
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>E-Voting Ketua OSIS</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f1f5f9;
            color: #1e293b;
            min-height: 100vh;
        }

        header {
            background: #123c69;
            color: white;
            padding: 25px 15px;
            text-align: center;
        }

        header h1 {
            font-size: 30px;
            margin-bottom: 10px;
        }

        header p {
            font-size: 15px;
            color: #dbeafe;
        }

        nav {
            background: white;
            display: flex;
            justify-content: center;
            gap: 10px;
            padding: 15px;
            flex-wrap: wrap;
            box-shadow: 0 2px 8px #00000010;
        }

        nav button {
            border: none;
            background: #e2e8f0;
            color: #1e293b;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        nav button:hover,
        nav button.active {
            background: #2563eb;
            color: white;
        }

        .container {
            max-width: 1100px;
            margin: 30px auto;
            padding: 0 20px;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        .welcome {
            background: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 25px;
            box-shadow: 0 4px 15px #00000008;
        }

        .welcome h2 {
            color: #123c69;
            margin-bottom: 12px;
        }

        .welcome p {
            line-height: 1.7;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }

        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            text-align: center;
            box-shadow: 0 4px 15px #00000008;
        }

        .stat-card h3 {
            font-size: 15px;
            color: #64748b;
            margin-bottom: 12px;
        }

        .stat-card p {
            font-size: 30px;
            font-weight: bold;
            color: #2563eb;
        }

        .panel {
            background: white;
            padding: 25px;
            border-radius: 12px;
            margin-bottom: 25px;
            box-shadow: 0 4px 15px #00000008;
        }

        .panel h2 {
            margin-bottom: 20px;
            color: #123c69;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 13px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            margin-bottom: 20px;
            font-size: 15px;
        }

        .candidates {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
        }

        .candidate {
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            padding: 20px;
            text-align: center;
            transition: 0.2s;
        }

        .candidate:hover {
            border-color: #2563eb;
            transform: translateY(-3px);
        }

        .candidate.selected {
            border-color: #2563eb;
            background: #eff6ff;
        }

        .candidate .avatar {
            width: 95px;
            height: 95px;
            border-radius: 50%;
            background: #dbeafe;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 45px;
            margin: 0 auto 15px;
        }

        .candidate h3 {
            margin-bottom: 8px;
        }

        .candidate p {
            color: #64748b;
            margin-bottom: 15px;
        }

        .candidate input[type="radio"] {
            width: 20px;
            height: 20px;
            margin: 0;
            cursor: pointer;
        }

        .btn {
            border: none;
            padding: 13px 20px;
            border-radius: 8px;
            font-size: 15px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
        }

        .btn-primary {
            background: #2563eb;
            color: white;
        }

        .btn-primary:hover {
            background: #1d4ed8;
        }

        .btn-success {
            background: #16a34a;
            color: white;
        }

        .btn-danger {
            background: #dc2626;
            color: white;
        }

        .btn:disabled {
            background: #94a3b8;
            cursor: not-allowed;
        }

        .full-width {
            width: 100%;
        }

        .notice {
            padding: 15px;
            border-radius: 8px;
            background: #eff6ff;
            color: #1d4ed8;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .success-message {
            padding: 20px;
            background: #dcfce7;
            color: #166534;
            border-radius: 10px;
            margin-top: 20px;
            line-height: 1.7;
        }

        .result-item {
            margin-bottom: 25px;
        }

        .result-info {
            display: flex;
            justify-content: space-between;
            gap: 10px;
            margin-bottom: 8px;
            flex-wrap: wrap;
        }

        .progress {
            background: #e2e8f0;
            height: 25px;
            border-radius: 20px;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            background: #2563eb;
            width: 0;
            transition: width 0.5s;
        }

        .footer {
            text-align: center;
            padding: 25px;
            background: #123c69;
            color: white;
            margin-top: 40px;
        }

        .small-text {
            font-size: 13px;
            color: #64748b;
            line-height: 1.6;
            margin-top: 15px;
        }

        @media (max-width: 600px) {
            header h1 {
                font-size: 23px;
            }

            .container {
                padding: 0 12px;
            }

            .panel,
            .welcome {
                padding: 20px;
            }

            nav button {
                padding: 10px 13px;
            }
        }
    </style>
</head>

<body>

    <header>
        <h1>🗳️ E-VOTING OSIS SMA UNGGULAN BADRIDDUJA </h1>
        <p>Sistem Pemilihan Ketua dan Wakil Ketua OSIS</p>
    </header>

    <nav>
        <button class="active" onclick="showPage('beranda', this)">
            Beranda
        </button>

        <button onclick="showPage('pemilihan', this)">
            Pemilihan
        </button>

        <button onclick="showPage('hasil', this)">
            Hasil Suara
        </button>
    </nav>

    <main class="container">

        <!-- HALAMAN BERANDA -->
        <section id="beranda" class="page active">

            <div class="welcome">
                <h2>Selamat Datang di E-Voting!</h2>

                <p>
                    E-Voting merupakan sistem pemilihan secara elektronik
                    yang memudahkan pemilih untuk menentukan kandidat
                    pilihannya dengan cepat dan praktis.
                </p>

                <br>

                <p>
                    Silakan masukkan nama, buka menu Pemilihan, lalu
                    pilih salah satu kandidat Ketua OSIS.
                </p>
            </div>

            <div class="stats">

                <div class="stat-card">
                    <h3>Jumlah Kandidat</h3>
                    <p id="jumlahKandidat">3</p>
                </div>

                <div class="stat-card">
                    <h3>Total Suara Masuk</h3>
                    <p id="totalBeranda">0</p>
                </div>

                <div class="stat-card">
                    <h3>Status Pemilihan</h3>
                    <p style="font-size: 22px;">Aktif</p>
                </div>

            </div>

            <div class="panel">
                <h2>📌 Petunjuk Pemilihan</h2>

                <ol style="line-height: 2; padding-left: 22px;">
                    <li>Masukkan nama pemilih.</li>
                    <li>Buka menu Pemilihan.</li>
                    <li>Pilih satu kandidat yang kamu inginkan.</li>
                    <li>Tekan tombol Kirim Suara.</li>
                    <li>Konfirmasikan pilihanmu.</li>
                    <li>Lihat hasil perolehan suara melalui menu Hasil Suara.</li>
                </ol>
            </div>

        </section>


        <!-- HALAMAN PEMILIHAN -->
        <section id="pemilihan" class="page">

            <div class="panel">

                <h2>🗳️ Formulir Pemilihan</h2>

                <div class="notice">
                    Pastikan nama sudah benar sebelum memberikan suara.
                    Dalam contoh ini, setiap browser hanya dapat menyimpan
                    satu suara.
                </div>

                <form id="formVoting">

                    <label for="namaPemilih">Nama Pemilih</label>

                    <input
                        type="text"
                        id="namaPemilih"
                        placeholder="Masukkan nama lengkap"
                        maxlength="100"
                        autocomplete="name"
                        required
                    >

                    <h2 style="margin-top: 10px;">
                        Pilih Kandidat Ketua OSIS
                    </h2>

                    <div class="candidates">

                        <!-- KANDIDAT 1 -->
                        <label class="candidate">

                            <div class="avatar">👨‍</div>

                            <h3>Kandidat Nomor 1</h3>

                            <p>Nadzir haramin</p>

                            <p>
                                Visi: Sekolah disiplin, aktif, dan berprestasi.
                            </p>

                            <input
                                type="radio"
                                name="kandidat"
                                value="1"
                                required
                            >

                            <div>Pilih Kandidat 1</div>

                        </label>


                        <!-- KANDIDAT 2 -->
                        <label class="candidate">

                            <img src="https://i.pinimg.com/200x150/82/47/a6/8247a6f8d2f5a4faf381b850bc3cfe69.jpg" alt="Foto Calon pertama" class="foto-calon">

                            <h3>Kandidat Nomor 2</h3>

                            <p>M.Arif hidayatullah</p>

                            <p>
                                Visi: Mewujudkan sekolah kreatif dan nyaman.
                            </p>

                            <input
                                type="radio"
                                name="kandidat"
                                value="2"
                                required
                            >

                            <div>Pilih Kandidat 2</div>

                        </label>


                        <!-- KANDIDAT 3 -->
                        <label class="candidate">

                            <div class="avatar">👨‍🎓</div>

                            <h3>Kandidat Nomor 3</h3>

                            <p>M.Sulton ali</p>

                            <p>
                                Visi: Mengembangkan bakat dan potensi siswa.
                            </p>

                            <input
                                type="radio"
                                name="kandidat"
                                value="3"
                                required
                            >

                            <div>Pilih Kandidat 3</div>

                        </label>

                    </div>

                    <button
                        type="submit"
                        class="btn btn-primary full-width"
                        id="tombolPilih"
                    >
                        KIRIM SUARA
                    </button>

                </form>

                <div id="pesanVoting"></div>

                <p class="small-text">
                    Nama dan pilihan kandidat disimpan di browser ini
                    sebagai contoh pembelajaran. Data tidak dikirim
                    ke server.
                </p>

            </div>

        </section>


        <!-- HALAMAN HASIL -->
        <section id="hasil" class="page">

            <div class="panel">

                <h2>📊 Hasil Perolehan Suara</h2>

                <div class="notice">
                    Hasil berikut berasal dari suara yang tersimpan
                    di browser ini, bukan dari seluruh perangkat pemilih.
                </div>

                <div class="stats">

                    <div class="stat-card">
                        <h3>Total Suara</h3>
                        <p id="totalHasil">0</p>
                    </div>

                    <div class="stat-card">
                        <h3>Kandidat Unggul</h3>
                        <p id="kandidatUnggul" style="font-size: 19px;">
                            Belum ada
                        </p>
                    </div>

                </div>

                <div id="daftarHasil"></div>

                <button
                    class="btn btn-primary"
                    onclick="perbaruiHasil()"
                >
                    PERBARUI HASIL
                </button>

            </div>

            <div class="panel">

                <h2>📋 Informasi Sistem</h2>

                <p style="line-height: 1.8;">
                    Sistem ini menggunakan penyimpanan lokal browser
                    (localStorage). Hasil dapat berbeda jika dibuka
                    di browser atau perangkat lain.
                </p>

                <p class="small-text">
                    Tombol penghapusan suara tidak disediakan pada halaman
                    pemilih. Untuk pengujian ulang, data dapat dihapus
                    melalui pengaturan penyimpanan situs pada browser.
                </p>

            </div>

        </section>

    </main>


    <footer class="footer">
        <p>© 2026 E-Voting OSIS | Sistem Pemilihan Elektronik</p>
        <p style="margin-top: 8px;">
            Dibuat untuk pembelajaran HTML, CSS, dan JavaScript.
        </p>
    </footer>


    <script>
        // DATA KANDIDAT
        const kandidat = [
            {
                id: "1",
                nama: "Nadzir haramin"
            },
            {
                id: "2",
                nama: "M.Arif hidayatullah"
            },
            {
                id: "3",
                nama: "M.Sulton ali"
            }
        ];

        // KUNCI PENYIMPANAN BROWSER
        const KEY_SUARA = "evoting_suara_demo_v1";
        const KEY_STATUS = "evoting_status_demo_v1";

        // MEMBACA DATA SUARA
        function bacaSuara() {
            try {
                const data = JSON.parse(
                    localStorage.getItem(KEY_SUARA)
                );

                if (!data || typeof data !== "object") {
                    return {
                        "1": 0,
                        "2": 0,
                        "3": 0
                    };
                }

                return {
                    "1": Math.max(0, Number(data["1"]) || 0),
                    "2": Math.max(0, Number(data["2"]) || 0),
                    "3": Math.max(0, Number(data["3"]) || 0)
                };

            } catch (error) {
                return {
                    "1": 0,
                    "2": 0,
                    "3": 0
                };
            }
        }


        // MEMBUKA HALAMAN
        function showPage(pageId, button) {

            document.querySelectorAll(".page").forEach(function(page) {
                page.classList.remove("active");
            });

            document.getElementById(pageId).classList.add("active");

            document.querySelectorAll("nav button").forEach(function(btn) {
                btn.classList.remove("active");
            });

            button.classList.add("active");

            if (pageId === "hasil") {
                perbaruiHasil();
            }

            if (pageId === "beranda") {
                perbaruiBeranda();
            }

            if (pageId === "pemilihan") {
                periksaStatusPemilih();
            }
        }


        // MEMERIKSA STATUS PEMILIH
        function periksaStatusPemilih() {

            const sudahMemilih =
                localStorage.getItem(KEY_STATUS) === "sudah";

            const tombol = document.getElementById("tombolPilih");
            const nama = document.getElementById("namaPemilih");
            const pesan = document.getElementById("pesanVoting");

            if (sudahMemilih) {

                tombol.disabled = true;
                nama.disabled = true;

                document.querySelectorAll(
                    'input[name="kandidat"]'
                ).forEach(function(input) {
                    input.disabled = true;
                });

                pesan.innerHTML = `
                    <div class="success-message">
                        <strong>Suara sudah diberikan.</strong><br>
                        Browser ini telah menyimpan satu suara.
                        Kamu tidak dapat memilih lagi menggunakan
                        penyimpanan browser yang sama.
                    </div>
                `;

            } else {

                tombol.disabled = false;
                nama.disabled = false;

                document.querySelectorAll(
                    'input[name="kandidat"]'
                ).forEach(function(input) {
                    input.disabled = false;
                });

                pesan.innerHTML = "";
            }
        }


        // PROSES MEMBERIKAN SUARA
        document.getElementById("formVoting").addEventListener(
            "submit",
            function(event) {

                event.preventDefault();

                if (localStorage.getItem(KEY_STATUS) === "sudah") {
                    alert("Browser ini sudah memberikan suara.");
                    periksaStatusPemilih();
                    return;
                }

                const nama = document
                    .getElementById("namaPemilih")
                    .value
                    .trim();

                const pilihan = document.querySelector(
                    'input[name="kandidat"]:checked'
                );

                if (!nama) {
                    alert("Silakan masukkan nama pemilih.");
                    return;
                }

                if (!pilihan) {
                    alert("Silakan pilih salah satu kandidat.");
                    return;
                }

                const kandidatDipilih = kandidat.find(function(item) {
                    return item.id === pilihan.value;
                });

                if (!kandidatDipilih) {
                    alert("Kandidat tidak ditemukan.");
                    return;
                }

                const konfirmasi = confirm(
                    "Nama pemilih: " + nama +
                    "\nPilihan: " + kandidatDipilih.nama +
                    "\n\nApakah kamu yakin ingin memberikan suara?"
                );

                if (!konfirmasi) {
                    return;
                }

                try {

                    const suara = bacaSuara();

                    suara[pilihan.value]++;

                    // Simpan hasil suara
                    localStorage.setItem(
                        KEY_SUARA,
                        JSON.stringify(suara)
                    );

                    // Tandai browser sudah memilih
                    localStorage.setItem(KEY_STATUS, "sudah");

                    // Simpan nama secara lokal untuk demo
                    localStorage.setItem(
                        "evoting_nama_demo_v1",
                        nama
                    );

                    document.getElementById("pesanVoting").innerHTML = `
                        <div class="success-message">
                            <strong>✓ Suara berhasil disimpan!</strong><br>
                            Terima kasih, ${escapeHTML(nama)}.
                            Pilihanmu telah tercatat pada browser ini.
                        </div>
                    `;

                    periksaStatusPemilih();
                    perbaruiBeranda();

                    alert("Suara berhasil disimpan!");

                } catch (error) {

                    alert(
                        "Data tidak dapat disimpan. " +
                        "Pastikan browser mengizinkan penyimpanan lokal."
                    );

                }

            }
        );


        // MENCEGAH NAMA DITAMPILKAN SEBAGAI HTML
        function escapeHTML(teks) {
            return teks.replace(/[&<>"']/g, function(karakter) {
                const pengganti = {
                    "&": "&amp;",
                    "<": "&lt;",
                    ">": "&gt;",
                    '"': "&quot;",
                    "'": "&#039;"
                };

                return pengganti[karakter];
            });
        }


        // MEMPERBARUI HALAMAN BERANDA
        function perbaruiBeranda() {

            const suara = bacaSuara();

            const total =
                suara["1"] +
                suara["2"] +
                suara["3"];

            document.getElementById("totalBeranda").textContent = total;

            document.getElementById("jumlahKandidat").textContent =
                kandidat.length;
        }


        // MENAMPILKAN HASIL SUARA
        function perbaruiHasil() {

            const suara = bacaSuara();

            const total =
                suara["1"] +
                suara["2"] +
                suara["3"];

            document.getElementById("totalHasil").textContent = total;

            const hasil = document.getElementById("daftarHasil");

            hasil.innerHTML = "";

            kandidat.forEach(function(item) {

                const jumlah = suara[item.id];

                const persentase = total > 0
                    ? (jumlah / total) * 100
                    : 0;

                const bagian = document.createElement("div");

                bagian.className = "result-item";

                const info = document.createElement("div");
                info.className = "result-info";

                const nama = document.createElement("strong");
                nama.textContent =
                    "Nomor " + item.id + " - " + item.nama;

                const angka = document.createElement("span");
                angka.textContent =
                    jumlah + " suara (" +
                    persentase.toFixed(1) + "%)";

                info.appendChild(nama);
                info.appendChild(angka);

                const progress = document.createElement("div");
                progress.className = "progress";

                const bar = document.createElement("div");
                bar.className = "progress-bar";
                bar.style.width = persentase + "%";

                progress.appendChild(bar);

                bagian.appendChild(info);
                bagian.appendChild(progress);

                hasil.appendChild(bagian);

            });

            const nilaiTertinggi = Math.max(
                suara["1"],
                suara["2"],
                suara["3"]
            );

            const pemenang = kandidat.filter(function(item) {
                return suara[item.id] === nilaiTertinggi;
            });

            let teksPemenang = "Belum ada";

            if (total > 0 && pemenang.length === 1) {
                teksPemenang = pemenang[0].nama;
            } else if (total > 0 && pemenang.length > 1) {
                teksPemenang = "Imbang";
            }

            document.getElementById("kandidatUnggul").textContent =
                teksPemenang;

        }


        // MENJALANKAN SAAT HALAMAN DIBUKA
        perbaruiBeranda();
        perbaruiHasil();
        periksaStatusPemilih();

    </script>

</body>
</html>
