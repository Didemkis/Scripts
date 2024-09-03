Mevcut sistem kaynaklarını izleyen bir betik.


```

#!/bin/bash
 
OUTPUT_FİLE="/root/system_usege.txt"

if [-f "$OUTPUT_FİLE"]; then
    echo "Eski dosya aranıyor ve siliniyor.."
    rm "$OUTPUT_FİLE"
fi

while true
do
    echo "Sistem kaykları - $(date)" >> $OUTPUT_FİLE
    echo "-------------------------" >> $OUTPUT_FİLE

    top -b -n 1 >> $OUTPUT_FİLE
    echo "" >> $OUTPUT_FİLE
    echo "Güncellendi. 10 sayine bekleniyor.."

    sleep 10 
done

```

while true ifadesi bir sonsuz döngü oluşturur. Döngü, durdurulana kadar sürekli çalışır. 

top -b -n 1: Bu komut, sistemin anlık durumunu (CPU bellek kullanımı vb.) metin tabanlı bir formatta (batch mode) tek seferde (-n 1) çıktılar.