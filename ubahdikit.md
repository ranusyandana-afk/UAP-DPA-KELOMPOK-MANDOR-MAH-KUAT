# UAP-DPA-KELOMPOK-MANDOR-MAH-KUAT

# STRUKTUR DATA
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

#UNTUK NAMBAH JADWAL
def tambah_jadwal():
     print("\n" + "="*30)
     print("        TAMBAH JADWAL")
     print("="*30)

     hari = input("Hari : ")
     matkul = input("Mata Kuliah    : ")
     jam = input("Waktu dan Tempat   : ")

     jadwal_kuliah.append({
          "hari": hari,
          "Mata Kuliah": matkul,
          "Waktu dan Tempat": jam
     })

     print(f"\n Jadwal '{matkul}' pada hari {hari} pukul {jam} berhasil ditambahkan!")


# UNTUK NAMPILIN JADWAL
def tampilkan_jadwal():
     print("\n" + "="*30)
     print("        DAFTAR JADWAL")
     print("="*30)

     if not jadwal_kuliah:
        print("Belum ada jadwal.")
        return
     
     print(f"{'No':<3} | {'Hari':<10} | {'Mata Kuliah':<15} | {'Waktu dan Tempat'}")
     print("-"*60)
     
     for i, item in enumerate(jadwal_kuliah, start=1):
          print(f"{i:<3} | {item['hari']:<10} | {item['Mata Kuliah']:<15} | {item['Waktu dan Tempat']}")


# UNTUK CARI JADWAL
def cari_jadwal():
     print("\n" + "="*30)
     print("        CARI JADWAL")
     print("="*30)
     
     keyword = input("Masukkan kata kunci (hari/mata kuliah): ").lower()
          
     hasil = []
     for item in jadwal_kuliah:
          if keyword in item['hari'].lower() or keyword in item['Mata Kuliah'].lower():
               hasil.append(item)

     if not hasil:
         print("Tidak ada jadwal yang cocok.")
     else:
         for i, item in enumerate(hasil, start=1):
             print(f"{i}. {item['hari']} | {item['Mata Kuliah']} | {item['Waktu dan Tempat']}")


# UNTUK EDIT JADWAL
def edit_jadwal():
    print("\n" + "="*30)
    print("        EDIT JADWAL")
    print("="*30)
    tampilkan_jadwal()

    if not jadwal_kuliah:
        return

    try:
        nomor = int(input("\nPilih nomor jadwal yang ingin diubah: "))
        index = nomor - 1

        if index < 0 or index >= len(jadwal_kuliah):
            print("Nomor tidak valid.")
            return

        print("Kosongkan jika tidak ingin mengubah.")

        hari_baru = input("Hari baru        : ")
        matkul_baru = input("Mata Kuliah baru : ")
        jam_baru = input("Waktu & Tempat baru : ")

        if hari_baru:
            jadwal_kuliah[index]["hari"] = hari_baru
        if matkul_baru:
            jadwal_kuliah[index]["Mata Kuliah"] = matkul_baru
        if jam_baru:
            jadwal_kuliah[index]["Waktu dan Tempat"] = jam_baru

        print("Jadwal berhasil diperbarui!")

    except ValueError:
        print("Input harus berupa angka.")


# UNTUK HAPUS JADWAL YANG DIINGINKAN
def hapus_jadwal():
    print("\n" + "="*30)
    print("        HAPUS JADWAL")
    print("="*30)
    tampilkan_jadwal()

    if not jadwal_kuliah:
        return

    try:
        nomor = int(input("Pilih nomor jadwal yang ingin dihapus: "))
        index = nomor - 1

        if index < 0 or index >= len(jadwal_kuliah):
            print("Nomor tidak valid.")
            return

        jadwal_kuliah.pop(index)
        print("Jadwal berhasil dihapus!")

    except ValueError:
        print("Input harus berupa angka.")


# BAGIAN MENU
def menu():
     while True:
          print("\n COLLEGE STUDY SCHEDLE MANAGER")
          print("1. Tambah Jadwal")
          print("2. Ubah Jadwal")
          print("3. Hapus Jadwal")
          print("4. Tampilkan Jadwal")
          print("5. Cari Jadwal")
          print("6. Keluar")

          pilih = input("Pilih Menu dari nomor(1-6) : ")
          if pilih == "1":
               tambah_jadwal()
          elif pilih == "2":
               edit_jadwal()
          elif pilih == "3":
               hapus_jadwal()
          elif pilih == "4":
               tampilkan_jadwal()
          elif pilih == "5":
               cari_jadwal()
          elif pilih == "6":
               print("\nProgram Selesai, Sampai Jumpa😊")
               break
          else:
               print("\nPilihan Tidak Valid, Silahkan pilih yang ada di menu😡")

menu()
