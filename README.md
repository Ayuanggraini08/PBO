# PBO
class Mahasiswa:
    def __init__(self, nama, npm, jurusan):
        self.nama = nama
        self.npm = npm
        self.jurusan = jurusan

    def tampilkan_info(self):
        print("Nama:", self.nama)
        print("NPM:", self.npm)
        print("Jurusan:", self.jurusan.nama_jurusan)
        print("Universitas:", self.jurusan.universitas.nama_universitas)


class Jurusan:
    def __init__(self, nama_jurusan, universitas):
        self.nama_jurusan = nama_jurusan
        self.universitas = universitas
        self.daftar_mahasiswa = []

    def tambah_mahasiswa(self, mahasiswa):
        self.daftar_mahasiswa.append(mahasiswa)

    def tampilkan_daftar_mahasiswa(self):
        print("Daftar Mahasiswa di Jurusan", self.nama_jurusan)
        for mahasiswa in self.daftar_mahasiswa:
            print("- Nama:", mahasiswa.nama)
            print("  NPM:", mahasiswa.npm)


class Universitas:
    def __init__(self, nama_universitas):
        self.nama_universitas = nama_universitas
        self.daftar_jurusan = []

    def tambah_jurusan(self, jurusan):
        self.daftar_jurusan.append(jurusan)

    def tampilkan_daftar_jurusan(self):
        print("Daftar Jurusan di Universitas", self.nama_universitas)
        for jurusan in self.daftar_jurusan:
            print("- Nama Jurusan:", jurusan.nama_jurusan)


# Membuat objek Universitas
universitas = Universitas("Universitas Bengkulu")

# Membuat objek Jurusan
jurusan1 = Jurusan("Teknik Informatika", universitas)

# Membuat objek Mahasiswa
mahasiswa1 = Mahasiswa("Ayu Anggraini", "G1A022007", jurusan1)

# Menambahkan mahasiswa ke dalam jurusan
jurusan1.tambah_mahasiswa(mahasiswa1)

# Menambahkan jurusan ke dalam universitas
universitas.tambah_jurusan(jurusan1)

# Menampilkan informasi mahasiswa
mahasiswa1.tampilkan_info()
