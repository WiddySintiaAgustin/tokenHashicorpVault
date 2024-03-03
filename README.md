## Active vault server ##
Mulai Vault dengan perintah vault server -config /etc/vault.d/vault.hcl
Kemudian jalankan perintah vault operator init -key-shares 5 -key-threshold 5.
Salin baik kunci utama (root key) maupun kunci unseal.
Mulai proses membuka segel Vault dengan menggunakan kunci membuka segel.
Selanjutnya, jalankan vault login dan masukkan token root.
Salin kunci unseal satu per satu ke dalam skrip bash unseal yang terletak di vault-management-*/script untuk mengotomatiskan operasi unseal nanti.
Jalankan perintah vault secrets enable -version=2 kv.
Jalankan perintah vault kv enable-versioning kv/.
Untuk memasukkan rahasia Vault untuk penggunaan pertama, gunakan vault kv put kv/[nama cabang] [kunci rahasia]=[nilai rahasia] [kunci rahasia]=[nilai rahasia].
Untuk memperbarui rahasia Vault, gunakan vault kv patch kv/[nama cabang] [kunci rahasia]=[nilai rahasia].
Untuk menghapus sepenuhnya nama cabang, gunakan vault kv metadata delete kv/[nama cabang].
Untuk menampilkan semua nama cabang, gunakan vault kv list kv
