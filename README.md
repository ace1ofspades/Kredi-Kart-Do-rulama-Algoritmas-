## Kredi Kartı Anatomisi Ve Luhn Algoritması
### Kredi Kartı Anatomisi:
##### Bir kredi kartı numarası, örneğin 1234567812345678, 3 bölümden oluşur:

  > - Banka Numarası(BIN):  İlk 6 hane, banka kimlik numarası (BIN) veya düzenleyici kimlik numarasıdır (IIN). Bu sayı dizisi, kartı vereni tanımlar.
  > - Hesap Numarası: Banka kimlik numarası ile kontrol hanesi arasındaki numara 6 ila 9 hane uzunluğundadır ve bireysel hesap numarasını tanımlamak için kullanılır.
  > - Kontrol Numarası: Son basamak kontrol basamağıdır ve kredi kartı numarasının gerçekliğini doğrulamak için eklenir (Luhn algoritmasına göre).

### Banka Kimlik Numarası (BIN) & İhraççı Bilgi Numarası (IIN) aralıkları

  Kartın ilk hanesi, kredi kartınızı veren sektör kategorisini (IIN) temsil eder. Örneğin VISA veya MasterCard kullanıyorsanız kartınızın ilk hanesi 4 veya 5 olmalıdır çünkü bunlar bankacılık ve finans sektöründendir. American Express seyahat kategorisindedir ve onlar tarafından verilen kartların ilk hanesi 3'tür. Bu nedenle bazı web siteleri, yalnızca bir tuşa basıldıktan sonra geçerli bir kart numarasını otomatik olarak tanımlayabilir.

```
                              ### Bank Identification Number (BIN)       Rakam Sayısı
        
American Express                            34|37                            15
Diners Club Carte Blanche                  300-305                           14
Diners Club International                    36                              14
Diners Club US and Canada                   54|55                            16
Discover Card                    6011|622126-622925|644-649|65               16
InstaPayment                              637-639                            16
JCB                                      3528-3589                           16
Laser                               6304|6706|6771|6709                    16-19
Maestro                   5018|5020|5038|6304|6759|6761|6762|6763.         12-19
Mastercard                                 51-55                             16
Visa                                         4                             13-16
Visa Electron                4026|417500|4508|4844|4913|4917                 16
```

### Luhn Algoritması ve MOD 10 Sağlaması
  Kredi kartı numaranızın son haneleri, sağlama toplamına benzer bir kontrol rakamıdır. Uygun kontrol hanesine ulaşmak için kullanılan algoritmaya, IBM bilim adamı Hans Peter Luhn'dan (1896-1964) sonra Luhn algoritması denir.
  Mod 10 hesaplaması olarak da bilinen LUHN algoritması, birincil hesap numaralarını doğrulamak için kullanılabilir.

#### Nasıl Çalışır?
##### Luhn algoritmasını elle hesaplamak birkaç farklı adımı içerir:
  1. Kredi kartı numarasını yazın
  > 4417 1234 5678 9113
  2. İlk sayıdan başlayarak, her çift basamağı ikiye katlayın
  > 4(x2) 4 1(x2) 7 1(x2) 2 3(x2) 4 5(x2) 6 7(x2) 8 9(x2) 1 1(x2) 3
  > Çift sayılar sonucu: 8 2 2 6 10 14 18 2
  3. İkiye katlamanın sonucu iki basamakla bitiyorsa, bu iki basamağı toplayın
  > 10 = 1+0 14= 1+4 18= 1+8
  4. tüm sayıları topla
  > 8+4+2+7 + 2+2+6+4 + 1+0+6+1+4+8 + 1+8+1+2+3 = 70
  
Son tutar 10'a bölünebiliyorsa, kredi kartı geçerlidir. 10'a bölünemiyorsa sayı geçersiz veya sahtedir. Yukarıdaki örnekte 4417 1234 5678 9113 numaralı kredi kartı Luhn testinden geçmiştir.
