# Struktur Data Nya
jadwal = [

    { "hari": "Senin", "Mata Kuliah": "DPA", "Waktu dan Tempat": "09.15-10.45, GIK L2" },
    { "hari": "Senin", "Mata Kuliah": "Praktikum DPA", "Waktu dan Tempat": "13.55-15.30, GIK L1B" },
    { "hari": "Selasa", "Mata Kuliah": "Bahasa Inggris", "Waktu dan Tempat": "07.30-09.00, GIK L1B" },
    { "hari": "Selasa", "Mata Kuliah": "Sains Dasar", "Waktu dan Tempat": "09.30-11.00, G Fisika Lt3" },
    { "hari": "Selasa", "Mata Kuliah": "Sains Dasar", "Waktu dan Tempat": "09.30-11.00, G Fisika Lt3" },
    { "hari": "Selasa", "Mata Kuliah": "PGAI", "Waktu dan Tempat": "13.55-15.30, GIK L2" },
    { "hari": "Rabu", "Mata Kuliah": "Logmat", "Waktu dan Tempat": "13.55-15.30, GIK L1C" },
    { "hari": "Rabu", "Mata Kuliah": "PTI", "Waktu dan Tempat": "15.55-17.30, GIK L1C" },
    { "hari": "Kamis", "Mata Kuliah": "KSI", "Waktu dan Tempat": "09.15-11.00, GIK L1B" },
    { "hari": "Kamis", "Mata Kuliah": "POK", "Waktu dan Tempat": "15.50-17.30, GIK L1B" },
]

jadwal = []

# Buat Nambaj Jadwal
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

# Buat Nampilin Jadwal
def tampilkan_jadwal():
    print("\n" + "="*30)
     print("        DAFTAR JADWAL")
     print("="*30)

    if not jadwal:
        print("Belum ada jadwal.")
        return
    
    for i, item in enumerate(jadwal, start=1):
        print(f"{i}. {item['hari']} | {item['mapel']} | {item['jam']}")

# Cari Jadwal Niii
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
