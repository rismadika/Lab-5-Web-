<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>FORM Validator</title>
	<style>
		form p > label {
			display: inline-block;
			clear: right;
			width: 100px;
			height: 20px;
		}
		form div > label {
			display: inline-block;
			width: 100px;
			height: 30px;
		}
		form input[type="text"], form textarea {
			border: 1px solid #197a43;
		}
		form input[type="submit"] {
			border: 1px solid #197a43;
			background-color: #197a43;
			color: #ffffff;
			font-weight: bold;
			padding: 5px 15px;
		}
		form input[type="reset"] {
			border: 1px solid #197a43;
			background-color: #197a43;
			color: #ffffff;
			font-weight: bold;
			padding: 5px 12px;
		}
	</style>
</head>
<body bgcolor="dcdcdc">
	<header>
		<h1>Form Pendaftaran Mahasiswa Baru</h1>
	</header>
		<form name="formPendaftaran" action="daftar.php" method="post" onsubmit="return validateForm()">
	<fieldset>
		<legend>Data Mahasiswa Baru</legend>	
		<div class="form-group">
			<label for="nama">Nama Lengkap</label>
			<input type="text" id="nama" name="nama" placeholder="Nama lengkap" class="form-control">
		</div>
		<div class="form-group">
			<label for="nomor">No. HP</label>
			<input type="number" id="nomor" name="nomor" placeholder="08xxxxxxxxxx" class="form-control">
		</div>
		<div class="form-group">
			<label for="email">E-mail</label>
			<input type="email" id="email" name="email" placeholder="email@gmail.com" class="form-control">
		</div>
		<div class="form-group">
            <label>Tanggal Lahir:</label>
            <input type="date" name="tanggal" />
        </div>
		<div class="form-group">
			<label>Jenis Kelamin</label>
			<input id="jk_l" type="radio" name="kelamin" value="L" /><label
for="jk_l">Laki-laki</label>
			<input id="jk_p" type="radio" name="kelamin" value="P" /><label
for="jk_p">Perempuan</label>
		</div>
		<div class="form-group">
			<label for="alamat">Alamat</label>
			<textarea id="alamat" name="alamat" placeholder="Alamat anda" cols="25" rows="4"></textarea>
		</div>
		<div class="form-group">
		<label>Pilih Jurusan</label>
		<select name="Pilih Jurusan">
			 <option value="TI"selected="selected">Teknik Informatika</option>
			 <option value="TK">Teknik Komputer</option>
			 <option value="TIN">Teknik Industri</option>
			 <option value="TS">Teknik Sipil</option>
			 <option value="TM">Teknik Mesin</option>
			 <option value="TL">Teknik Lingkungan</option>
		</select>
		</div>
		<p><input type="submit" name="tombol" value="Kirim" </p>
		<p><input type="reset" name="tombol2" value="Hapus" </p>
</form>
		<script>
        function validateForm() {
            if (document.forms["formPendaftaran"]["nama"].value == "") {
                alert("Nama Tidak Boleh Kosong");
                document.forms["formPendaftaran"]["nama"].focus();
                return false;
            }
			if (document.forms["formPendaftaran"]["nomor"].value == "") {
                alert("Nomor Tidak Boleh Kosong");
                document.forms["formPendaftaran"]["nomor"].focus();
                return false;
            }
			if (document.forms["formPendaftaran"]["email"].value == "") {
                alert("Email Tidak Boleh Kosong");
                document.forms["formPendaftaran"]["email"].focus();
                return false;
            }
			if (document.forms["formPendaftaran"]["tanggal"].value == "") {
                alert("Tempat, tanggal lahir Tidak Boleh Kosong");
                document.forms["formPendaftaran"]["tanggal"].focus();
                return false;
            }
			if (document.forms["formPendaftaran"]["kelamin"].value == ""){
                alert("Pilih jenis kelamin");
                document.forms["formPendaftaran"]["kelamin"].focus();
                return false;
            }
			if (document.forms["formPendaftaran"]["alamat"].value == "") {
                alert("Alamat Tidak Boleh Kosong");
                document.forms["formPendaftaran"]["alamat"].focus();
                return false;
			}
            if (document.forms["formPendaftaran"]["Pilih Jurusan"].selectedIndex < 1) {
                alert("Pilih Jurusan.");
                document.forms["formPendaftaran"]["Pilih Jurusan"].focus();
                return false;
            }
        }
    </script>
</body>
</html>
