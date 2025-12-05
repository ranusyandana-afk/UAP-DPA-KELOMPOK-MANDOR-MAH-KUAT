# UAP-DPA-KELOMPOK-MANDOR-MAH-KUAT
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
