1. Örnek 

Mevcut ağ bağlantılarını listeleyen bir betik.


Öncelikle list_coonnection.sh dosyamı oluşturuyorum.

```
#!/bin/bash

OUTPUT_FİLE =" /root/connection.txt"

if [-f "$OUTPUT_FİLE"]; then
    echo "Eski dosya bulunuyor ve siliniyor.."
    rm "$OUTPUT_FİLE"
fi

echo "Ağ Bağlantıları- $(date)" > $OUTPUT_FİLE
echo "------------------------------" >> $OUTPUT_FİLE

echo "Netstat Çıktısı:" >> $OUTPUT_FİLE
echo "----------------" >> $OUTPUT_FİLE
netstat -tulnp >> $OUTPUT_FİLE 2>&1
echo "" >> $OUTPUT_FİLE

echo "SS Çıktısı:" >> $OUTPUT_FİLE
echo "-----------" >> $OUTPUT_FİLE

```

```
KODUN AÇIKLAMASI

#!/bin/bash: Bu, betiğin hangi kabuk (shell) ile çalıştırılacağını belirtir.

OUTPUT_FILE="/root/connections.txt": Betik tarafından oluşturulacak olan dosyanın yolunu tanımlar.

if [ -f "$OUTPUT_FILE" ]; then ... fi: Eğer connections.txt dosyası daha önce mevcutsa, eski dosya silinir.

echo "Ağ Bağlantıları - $(date)" > $OUTPUT_FILE: Dosyanın başına tarih ve saat bilgisi ekler.

netstat -tulnp ve ss -tulnp komutları, TCP/UDP protokollerini kullanan aktif bağlantıları ve bu bağlantılara ait süreç bilgilerini listeler. Çıktılar dosyaya yazılır.

2>&1 standart hatayı (stderr) standart çıktı (stdout) ile aynı konuma yönlendirmek için kullanılır. 

```

###2. Örnek 
##Mevcut sistem kaynaklarını izleyen bir betik.









###3. Örnek 
##Disk kullanımını kontrol eden bir betik. Disk kullanımı %80'in üzerinde olan dosya sistemlerini tespit edip, bu durumu e-posta ile raporlayınız.



