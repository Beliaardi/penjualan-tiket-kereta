# penjualan-tiket-kereta
membuat laporan penjualan tiket kereta menggunakan python

import pandas as pd
#variable yg berulng menggunakan List/matriks
print("                                        PEMESANAN TIKET ANTAR ONLINE                                        ")
print("============================================================================================================")
list_pemesan=int(input("Masukan Jumlah Pemesan : "))
list_nama=[]
list_kode=[]
list_kereta=[]
list_beli=[]
list_harga=[]
list_jumlah=[]
list_total=[]
list_sub=[]

i=0
for i in range(list_pemesan):
    print ("Data ke - " +str(i+1))
    list_nama.append(input("Nama Pemesan : "))
    list_kode.append(input("Kode Kereta [1/2/3/4] : "))
    list_beli.append(int(input("Masukan Jumlah Beli : ")))

    if list_kode[i] == "1" :
        list_kereta.append("Argo Bromo")
        list_harga.append("150000")
        list_jumlah.append(list_beli[i]*int("150000"))
    elif list_kode[i] == "2" :
        list_kereta.append("Parahyangan")
        list_harga.append("100000")
        list_jumlah.append(list_beli[i]*int("100000"))
    elif list_kode[i] == "3" :
        list_kereta.append("Sembrani")
        list_harga.append("95000")
        list_jumlah.append(list_beli[i]*int("95000"))
    elif list_kode[i] == "4" :
        list_kereta.append("Argo Lawu")
        list_harga.append("80000")
        list_jumlah.append(list_beli[i]*int("80000"))
    else:
        list_kereta.append("Salah Input Kode")
        list_harga.append("0")
        list_jumlah.append(list_beli[i]*int("0"))
    i=i+1

#proses
for i in range(list_pemesan):
    list_total.append(int(list_beli[i] * int(list_harga[i])))
    list_sub = sum(list_total)

tamu = {
    "Nama Pemesan" : list_nama,
    "Kode Kereta" : list_kode,
    "Nama Kereta" : list_kereta,
    "Jumlah Beli" : list_beli,
    "Harga Tiket" : list_harga,
    "Total Bayar" : list_total
}
data_tamu = pd.DataFrame(tamu)
#cetak
print("=============================================================================================================")
print("                                                                                                             ")
print("=============================================================================================================")
print("                                      LAPORAN PENJUALAN TIKET ONLINE                                       ")
print("=============================================================================================================")
print(data_tamu)
print("=============================================================================================================")
print("                                                           Sub Total Rp. ", (list_sub))
