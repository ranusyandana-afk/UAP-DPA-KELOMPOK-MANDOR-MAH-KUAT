# UAP-DPA-KELOMPOK-MANDOR-MAH-KUAT
     
 ```python   
jadwal_kuliah = [

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
```

---


jadwal_kuliah = []

def tambah_jadwal():
     print("\n=====Tambah Jadwal=====")

     hari = input("Hari : ")
     matkul = input("Mata Kuliah    : ")
     jam = input("Jam   : ")

     jadwal_kuliah.append({
          "Hari": hari,          
          "Mata Kuliah": matkul,
          "Jam": jam
     })

     print(f"\n Jadwal '{matkul}' pada hari {hari} pukul {jam} berhasil ditambahkan!")
def tampilkan_jadwal():
    print("\n=== DAFTAR JADWAL ===")

    if not jadwal:
        print("Belum ada jadwal.")
        return
    
    for i, item in enumerate(jadwal, start=1):
        print(f"{i}. {item['hari']} | {item['mapel']} | {item['jam']}")
def cari_jadwal():
    print("\n=== CARI JADWAL ===")
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
def edit_jadwal():
    print("\n=== EDIT JADWAL ===")
    tampilkan_jadwal()

    if not jadwal:
        return

    try:
        nomor = int(input("Pilih nomor jadwal yang ingin diubah: "))
        index = nomor - 1

        if index < 0 or index >= len(jadwal):
            print("Nomor tidak valid.")
            return

        print("Kosongkan jika tidak ingin mengubah.")

        hari_baru = input("Hari baru        : ")
        mapel_baru = input("Mapel baru       : ")
        jam_baru = input("Jam belajar baru : ")

        if hari_baru:
            jadwal[index]["hari"] = hari_baru
        if mapel_baru:
            jadwal[index]["mapel"] = mapel_baru
        if jam_baru:
            jadwal[index]["jam"] = jam_baru

        print("Jadwal berhasil diperbarui!")

    except ValueError:
        print("Input harus berupa angka.")



def hapus_jadwal():
    print("\n=== HAPUS JADWAL ===")
    tampilkan_jadwal()

    if not jadwal:
        return

    try:
        nomor = int(input("Pilih nomor jadwal yang ingin dihapus: "))
        index = nomor - 1

        if index < 0 or index >= len(jadwal):
            print("Nomor tidak valid.")
            return

        jadwal.remove(jadwal[index])
        print("Jadwal berhasil dihapus!")

    except ValueError:
        print("Input harus berupa angka.")



def menu():

    while True:
        print("\n======== STUDY SCHEDULE MANAGER ========")
        print("1. Tambah Jadwal")
        print("2. Tampilkan Jadwal")
        print("3. Cari Jadwal")
        print("4. Edit Jadwal")
        print("5. Hapus Jadwal")
        print("6. Keluar")

        pilihan = input("Pilih menu (1-6): ")

        if pilihan == "1":
            tambah_jadwal()
        elif pilihan == "2":
            tampilkan_jadwal()
        elif pilihan == "3":
            cari_jadwal()
        elif pilihan == "4":
            edit_jadwal()
        elif pilihan == "5":
            hapus_jadwal()
        elif pilihan == "6":
            print("Program selesai. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid. Coba lagi.")

menu()



