print(" Nama : Valentino Silalahi ")
print(" Nim  : 2310431015 ")
print(" Program nilai ujian mahasiswa ")
print("=====================================================================")

n = int (input (" Masukkan jumlah mahasiswa   =  "))
m = int (input (" Masukkan jumlah mata kuliah =  "))

nmh = []
print(f" Masukkan {n} nama mahasiswa : ")
for i in range(n):
    mh = (input(f"Nama ke- {i+1} : "))
    nmh.append(mh)
print()

nmk = []
print(f" Masukkan {m} mata kuliah : ")
for i in range (m):
    mk = (input(f"Matkul ke- {i+1} : "))
    nmk.append(mk)
print()

nmhk = []
print(" Masukkan nilai-nilai mahasiswa pada setiap matkul ")
for i in range (n):
    baris = []
    print(f"Masukkan nilai untuk {nmh[i]}:")
    for j in range (m):
        nl = float (input (f"Nilai matkul {nmk[j]} = "))
        baris.append(nl)
    nmhk.append(baris)
print()

print("=====================================================================")
print("| Nama Mahasiswa |", end="")
for i in range(m):
    print(f" { nmk[i]:<10} | ", end="")
print("\n=====================================================================")

for i in range(n):
    print(f"| {nmh[i]:<14} |", end="")
    for j in range(m):
        print(f" {nmhk[i][j]:<10} | ", end="")
    print("\n---------------------------------------------------------------------")
print()

rtm = []
for i in range (n):
    tn = sum(nmhk[i])
    rt = tn/m
    rtm.append(rt)

print("\n============================================================")
print("| Nama Mahasiswa | Rata-rata Nilai Ujian |")
print("============================================================")
for i in range(n):
    print(f"| {nmh[i]:<14} | {rtm[i]:<21.2f} |")
print("============================================================")
print()

nl_t = [float('-inf')] * m
nl_r = [float('inf')] * m
nm_t = [''] * m
nm_r = [''] * m

for j in range(m):
    for i in range(n):
        if nmhk[i][j] > nl_t[j]:
            nl_t[j] = nmhk[i][j]
            nm_t[j] = nmh[i]
        if nmhk[i][j] < nl_r[j]:
            nl_r[j] = nmhk[i][j]
            nm_r[j] = nmh[i]

print("\nMahasiswa dengan Nilai Tertinggi dan Terendah untuk Setiap Mata Kuliah:")
for i in range(m):
    print(f"\nMata Kuliah: {nmk[i]}")
    print(f"Nilai Tertinggi: {nl_t[i]} oleh {nm_t[i]}")
    print(f"Nilai Terendah: {nl_r[i]} oleh {nm_r[i]}")
