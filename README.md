# Bolu Contoh — Demo Trial

Purwarupa SaaS untuk UMKM bolu pre-order yang menyatukan **ERP + SCM + CRM** dalam satu data bersama.

## Buka demo

**https://fatinarachmaputria.github.io/bolu-conto-demo/**

Tidak perlu instal apa pun. Semua data adalah **dummy** dan disimpan di browser Anda (`localStorage`), jadi setiap pengunjung punya datanya sendiri.

> Login pura-pura: cukup pilih peran **Pemesan** atau **Pemilik**. Tidak ada password, tidak ada keamanan sungguhan.

## Alur coba (5 menit)

1. **Masuk sebagai Pemesan** → pilih PO “PO Selasa — 18 Nov”.
2. Isi jumlah (mis. Bolu Original × 2), nama, dan nomor telepon → **Kirim pesanan**. Catat kode pesanan.
3. Pilih **Transfer**, isi nominal sesuai total, unggah gambar apa saja sebagai bukti (< 400 KB) → **Kirim bukti pembayaran**.
4. Klik **Masuk sebagai Pemilik** → menu **Pembayaran** → **Terima — Lunas**.
5. Menu **Batch PO** → **TUTUP PO** (PO hilang dari halaman publik).
6. Menu **Kebutuhan Bahan** → pilih “PO Uji Minimum — 17 Nov” (28 pcs) → lihat **Tepung terigu = 28 gr** dari resep 30 gr/30 pcs.
7. **Buat draf pembelian** → **Pemasok & Belanja** → **Tandai dipesan** → **Barang diterima (+ stok)** → cek **Bahan & Stok**.
8. **Pengaturan** → **Reset data contoh** untuk mengulang dari awal.

## Aturan hitung yang diuji

```
kebutuhan = takaran_resep × (total_pcs_varian ÷ ukuran_resep)
kekurangan = max(0, kebutuhan − stok)
```

- 30 gr / 30 pcs, pesan 30 pcs → **30 gr**
- 28 pcs → **28 gr**
- 65 pcs → **65 gr** (tanpa pembulatan ke kelipatan resep)
- Satuan hitung (butir/bungkus/pcs) dibulatkan ke atas hanya saat belanja.

## Catatan

- Repo ini hanya berisi **hasil build statis** untuk keperluan trial.
- Kode sumber lengkap ada di repo proyek (privat); hubungi pemilik repo untuk akses.
- Bukan sistem produksi: tanpa backend, autentikasi, payment gateway, atau notifikasi.
