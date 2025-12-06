# UAP-DPA-KELOMPOK-MANDOR-MAH-KUAT
jadwal = []

# Fungsi Untuk Menambah Jadwal Baru
def tambah_jadwal():
     print("\n" + "="*30)
     print("        TAMBAH JADWAL")
     print("="*30)
     hari = input("Hari : ")
     matkul = input("Mata Kuliah    : ")
     jam = input("Jam   : ")

     jadwal_kuliah.append({
          "Hari": hari,          
          "Mata Kuliah": matkul,
          "Jam": jam
     })

     print(f"\n Jadwal '{matkul}' pada hari {hari} pukul {jam} berhasil ditambahkan!")

# Fungsi Untuk Menampilkan Jadwal
def tampilkan_jadwal():
    print("\n" + "="*30)
     print("        DAFTAR JADWAL")
     print("="*30)

    if not jadwal:
        print("Belum ada jadwal.")
        return
    
    for i, item in enumerate(jadwal, start=1):
        print(f"{i}. {item['hari']} | {item['mapel']} | {item['jam']}")

# Fungsi Untuk Mencari Sebuah Jadwal
def cari_jadwal():
    print("\n" + "="*30)
     print("        CARI JADWAL")
     print("="*30)
    keyword = input("Masukkan kata kunci (hari/mapel): ").lower()

    hasil = []
    for item in jadwal:
        if keyword in item['hari'].lower() or keyword in item['mapel'].lower():
            hasil.append(item)
    
    if not hasil:
        print("Tidak ada jadwal yang cocok.")
    else:
        for i, item in enumerate(hasil, start=1):
            print(f"{i}. {item['hari']} | {item['mapel']} | {item['jam']}")



