```markdown
# 🚀 Kullanışı sed Komutları Cheetsheat

Bu Cheetsheat, GNU sed (stream editor) komutlarının kullanımını gösterir.

## 📝 Temel Kullanım

```bash
sed 'komut' dosya.txt
```

## 🔄 Metin Değiştirme

```bash
sed 's/old/new/g' dosya.txt                 # Her satırdaki "old" ifadesini "new" ile değiştirir.
sed 's/old/new/2' dosya.txt                 # Her satırın ikinci "old" ifadesini "new" ile değiştirir.
sed 's/old/new/gi' dosya.txt                # "old" ifadesini "new" ile değiştirirken büyük/küçük harf duyarlılığını göz ardı eder.
sed 's/\/old/\/new/g' dosya.txt             # Eğik çizgi (/) içeren ifadeleri değiştirir.
```

## 🗑️ Satır Silme

```bash
sed '4d' dosya.txt                          # Dördüncü satırı siler.
sed '2,5d' dosya.txt                        # İkinci ile beşinci satırlar arasındaki satırları siler.
sed '/pattern/d' dosya.txt                  # "pattern" ifadesine sahip satırları siler.
sed '/pattern/!d' dosya.txt                 # "pattern" ifadesine sahip olmayan satırları siler.
sed '/^$/d' dosya.txt                       # Boş satırları siler.
```

## ➕ Satır Ekleme

```bash
sed '2i\Yeni satır' dosya.txt               # İkinci satıra "Yeni satır" ekler.
sed '4a\Yeni satır' dosya.txt               # Dördüncü satırdan sonra "Yeni satır" ekler.
```

## 🔄 Dosya Yedekleme

```bash
sed -i.bak 's/old/new/g' dosya.txt          # "dosya.txt" dosyasındaki "old" ifadelerini "new" ile değiştirirken "dosya.txt.bak" adında yedek dosyası oluşturur.
```

## 🔎 İfade Eşleme

```bash
sed '/pattern/!d' dosya.txt                 # "pattern" ifadesine sahip olmayan satırları siler.
sed '/^$/d' dosya.txt                       # Boş satırları siler.
```

## 📄 Metin Kesme

```bash
sed 's/:/ /g' dosya.txt                     # ":" karakterini boşlukla değiştirir.
sed -n '2,5p' dosya.txt                     # İkinci ile beşinci satırları yazdırır.
```

## 📚 İfade Yerine Başka Bir Dosya İçeriği Eklemek

```bash
sed '/pattern/r dosya2.txt' dosya.txt       # "pattern" ifadesini içeren her satıra, "dosya2.txt" dosyasının içeriğini ekler.
```

## 🌈 Koşullu İşlemler

```bash
sed '/pattern/{s/old/new/g}' dosya.txt      # "pattern" ifadesini içeren satırlarda "old" ifadelerini "new" ile değiştirir.
```

## 🔄 Değişken Kullanımı

```bash
sed "s/$var/yeni_değer/g" dosya.txt         # Bash değişkenini kullanarak metni değiştirir. (var değişkeni önceden tanımlanmalıdır)
```

## 🎯 Düzenli İfadeler

```bash
sed '/^begin/,/^end/d' dosya.txt            # "begin" ifadesinden "end" ifadesine kadar olan satırları siler.
```

## ➡️ Çoklu Düzenlemeler

```bash
sed -e 's/old/new/g' -e 's/foo/bar/g' dosya.txt   # Birden fazla `sed` komutunu aynı satırda çalıştırır.
```

## 🏷️ Aralık İşaretleyicisi

```bash
sed '2,/pattern/d' dosya.txt                # İkinci satırdan "pattern" ifadesine kadar olan satırları siler.
```

## 🔢 Satır Numaralandırma

```bash
sed '=' dosya.txt | sed 'N; s/\n/\t/'       # Her satırın başına numara ekler.
```

## 📝 Metin Formatlama

```bash
sed -e :a -e 's/^.\{1,79\}$/&;/;ta' dosya.txt   # Her satırı 79 karaktere kadar kırpıp sonuna noktalı virgül ekler.
```

## 💾 Komut Dosyası Kullanımı

```bash
sed -f komutdosyasi.sed dosya.txt           # Belirli bir komut dosyasını kullanarak `sed` işlemlerini uygular.
```
```
