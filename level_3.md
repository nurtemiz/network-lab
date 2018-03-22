### WAN SİMÜLASYONU

![image3.1](/images/level_3/3_24.png)

**1. WAN Cihazları**

**1.1. Wide Area Network (WAN)**

Büyük bir coğrafi alana yayılmış bilgisayar ağına WAN-Geniş Alan Ağı denir. Diğer bir deyişle bir WAN, iki veya daha fazla yerel alan ağının [Local Area Network-LAN] birleştirilmiş halidir. Farklı yerel alan ağlarının haberleşmesidir. 

Çoğunlukla public network olarak isimlendirilen telefon şebekesi, ATM, Frame Relay, uydu, kiralık hatlar, TDM üzerinden oluşturulurlar. Dünyadaki en büyük WAN, Internet'tir.

**1.2. WAN Cihazları**

•	ADSL Modem
•	Yönlendirici (router)

**2. Yönlendirici – Yönlendirici Bağlantısı**

Yerel ağda bağlantı için ethernet kabloları kullanılır. Bir yönlendirici yerel ağ bağlanırken “Ethernet” (veya Fast Ethernet) portundan bağlantı yapılır. Fakat yerel ağın dışına çıkarken yönlendiricilerin “Ethernet” portları kullanılmaz. Yönlendiriciler birbirine bağlanırken seri port (Serial Port) kullanılır. 

**3. DCE ve DTE Bağlantıları**

Seri portla birbirine bağlı iki yönlendirici üzerinde, mantıksal bir ayrım yapmak için kullanılan bir yapıdır. Seri porttan haberleşen cihazlarda bir tarafın DCE (Data Communications Equipment) diğer tarafında DTE (Data Terminal Equipment) olması gerekir. 

Yönlendirici yapılandırmasında iki yönlendirici arasında veri iletim hızının belirlenmesi gerekir. DCE olan taraf, veri iletimindeki hızı belirleyen taraftır. DTE olan taraf ise belirlenen hızda veri iletimine katılan hısımdır.

![image3.2](/images/level_3/3_1.png)

![image3.3](/images/level_3/3_2.png)

_Şekil-1 Yönlendiriciye seri port modülü ekleme_

Ağ simülasyon yazılımında yönlendiriciler çalışma alanına eklendiklerinde üzerlerinde seri port bulunmaz. Bunun için yönlendirici üzerinde çift tıklayarak yönlendirici yönetim penceresinde Fiziksel (Physical) sekmesinde, seri port eklemek gerekmektedir. Bu işlem için önce yönlendirici güç (power) tuşu kapatılır ve ardından WIC-2T modülü sürükle bırak yöntemiyle boş bir yuvaya takılır.

![image3.4](/images/level_3/3_3.png)

_Şekil-2 WAN modeli_

Şekil-2 deki yönlendiricilerin tümü, seri kablo ile birbirine bağlanmıştır. Resimde bağlantının yapıldığı portların isimleri de görüntülenmektedir. Bazı port isimlerinin yanında, küçük bir saat simgesi dikkatinizi çekecektir. Bu simgenin görüldüğü port, mantıksal olarak diğer cihazla yapılan bağlantıdaki hızın belirlendiği porttur yani DCE kısmıdır.

Dikkat ederseniz saat simgesinin bulunduğu portun bağlı olduğu diğer yönlendiricideki portta, saat sinyali yoktur. İki saat sinyalinin olması bir çakışma yaratır. İki yönlendirici arasında bir bağlantı yapılandırılırken yönlendiricilerden sadece biri iletişim hızının belirlenmesinden sorumlu tutulur.

**4.	Anahtar – Yönlendirici Bağlantısı**

•	Çalışma alanına bir anahtar ve bir yönlendirici eklenerek bağlantılar (Connections) bölümünden, düz kablo seçildi.

•	Yönlendiricinin üzerinde, “FastEthernet” portlarından birine bağlantı yapıldı. Anahtar üzerinde de boşta olan bir porta bağlantı yapıldı.

•	İletişimin başlaması için kapalı olan yönlendirici portlarının açılması ve yapılandırılması gerekmektedir.

•	Kapalı olan yönlendirici portlarını açmak için ayar (config) sekmesinde “FastEthernet” bölümü seçilir ve sağ tarafta “Port Status” bölümü açık (ON) konumuna getirilir.

![image3.5](/images/level_3/3_4.png)

_Şekil-3 Yönlendirici anahtar bağlantısı_

**5.	PC – Anahtar Bağlantısı**

PC ile anahtar arasında düz kablo kullanılır. Bağlantılar bölümünden düz kablo seçilir. Önce anahtar üzerinde boş bir port seçilir. Ardından bağlantının PC’ye aktarılması için PC seçilir. Bilgisayar yerel ağa, “Ethernet” portundan bağlanacağı için biz burada “FastEthernet”i seçeceğiz.

**6.	PC Yapılandırması**

PC yapılandırması işlemi, bilgisayara TCP parametrelerinin (IP adresi, alt ağ maskesi, varsayılan ağ geçidi) atanması işlemidir. Bilgisayarların iletişim kurabilmeleri için paketlerin yerel ağın dışında dolaşabilmesi gerekmektedir. Bu işlemi yönlendiriciler gerçekleştirecektir.
 
![image3.6](/images/level_3/3_5.png)

_Şekil-4 PC yapılandırma_

**7.	Yönlendirici Yapılandırması**

Yönlendiriciler yapılandırılırken hem yerel ağa bağlı olan hem de dış ağlara bağlı olan portlarının yapılandırılması gerekmektedir. Resim 3.11’de bulunan yönlendiriciler hem yerel ağa bağlı hem de birbirleri arasındaki bağlantı sebebiyle dış ağa bağlıdır. Bu tasarımda üç adet ağ bulunmaktadır. Birinci ağ, Ogr1 isimli bilgisayarın bulunduğu yerel ağdır. 

İkinci ağ, Ogr2 isimli bilgisayarın bulunduğu yerele ağdır. 

Üçüncü ağ ise iki yönlendirici arasında kalan ( Resimde yerel ağ gibi görünse de bu iki yönlendiricinin arasına yüzlerce farklı yönlendiricini girebileceği bir telekom ağı olarak da düşünülebilir.) dış ağdır.

![image3.7](/images/level_3/3_6.png)

![image3.8](/images/level_3/3_7.png)

![image3.9](/images/level_3/3_8.png)

![image3.10](/images/level_3/3_9.png)

_Şekil-5 Yönlendirici yapılandırması_

**8.	Yönlendirme Yapılandırması**

Yönlendirme işlemi; temelde her yönlendiricinin kendisine bağlı bulunan diğer ağlarının bilgilerini, başka yönlendiricilerle paylaşmasıdır. Bu, farklı protokollerle gerçekleşebilir. 

Bu aşamada yönlendiriciler için tasarlanmış olan RIP yönlendirme protokolünün yapılandırmasını inceleyelim. Resim-6 da dinamik yönlendirme işleminin yapılışı gösterilmektedir.

![image3.11](/images/level_3/3_10.png)

![image3.12](/images/level_3/3_11.png)

_Şekil-6 Samsun ve İstanbul yönlendiricilerinin dinamik yönlendirilmesi_

**9.	Test İşlemleri**

Yönlendirme yapılandırması konusunda tasarlanan ağ için açıklanan işlemler yapıldıktan sonra, simülasyon kipine geçerek ARP ve ICMP protokollerini seçerek basit bir test işlemi gerçekleştirilir. 

Ogr2 bilgisayarından, Ogr1 bilgisayarına gönderilecek basit bir paket simülasyonu hazırlanır. Bu işlemin aynısı, bilgisayarların masaüstünde bulunan komut satırı programı, ping komutuyla da yapılabilir.

![image3.13](/images/level_3/3_12.png)

_Şekil-7 Bağlantının komut satırından test edilmesi_

![image3.14](/images/level_3/3_13.png) 

_Şekil-8 Bağlantının paket gönderilerek test edilmesi_

#### UYGULAMA

•	Çalışma alanına iki yönlendirici, üç dağıtıcı ve üç bilgisayar yerleştirilmesi. Tüm cihazları föyde verildiği gibi isimlendirildi.

•	Bilişim ve Elektronik yönlendiricilerinin birbirine bağlamak için Seri (Serial) port takıldı. (Yönlendirici yönetim penceresin Fiziksel sekmesinde bulunan WIC-1T modülü kullanıldı.)

•	Bilişim yönlendiricisi diğer cihazlara bağlandı. Bilişim yönlendiricisinin S0/1/0 portu elektronik yönlendiricisinin S0/1/0 portuna, FA0/0 portu Lab1 dağıtıcısına, FA0/1 portu Lab2 dağıtıcısına bağlanır.

•	Elektronik yönlendiricisi diğer cihazlara bağlandı. Elektronik yönlendiricisinin S0/1/0 portu Bilişim yönlendiricisini S0/1/0 portuna FA0/0 portu Lab dağıtıcısına bağlanır.

![image3.15](/images/level_3/3_14.png) 

_Şekil-9_

•	Bilişim yönlendiricisinin portlarına IP atması yapıldı.

S0/1/0 IP No: 192.168.0.1 Ağ maskesi: 255.255.255.0

FA0/0 IP No: 192.168.1.1 Ağ maskesi: 255.255.255.0

FA0/1 IP No: 192.168.2.1  Ağ maskesi 255.255.255.0

![image3.16](/images/level_3/3_15.png) 

![image3.17](/images/level_3/3_16.png) 

![image3.18](/images/level_3/3_17.png)

_Şekil-10_

•	Elektronik yönlendiricisinin portlarına IP atması yapıldı. 

S0/1/0 IP No: 192.168.0.2 Ağ maskesi: 255.255.255.0

FA0/0 IP No: 192.168.3.1 Ağ maskesi: 255.255.255.0

![image3.19](/images/level_3/3_18.png) 

![image3.20](/images/level_3/3_19.png) 

_Şekil-11_

•	Bilgisayarlar için IP numarası, ağ maskesi ve varsayılan ağ geçidi bilgilerinin girilmesi.

Bil1 için: IP No: 192.168.1.10, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.1.1

Bil2 için: IP No: 192.168.2.10, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.2.1

Bil için: IP No: 192.168.3.10, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.3.1 

![image3.21](/images/level_3/3_20.png) 

_Şekil-12_

•	Yönlendiricilerin yönlendirme bilgilerini güncellemek için dinamik yönlendirme işlemini geçekleştirilmesi. 

(Yönlendirici yönetim penceresinde ayarlar (Config) sekmesinde RIP bölümüne seçili yönlendiricinin bağlı bulunduğu ağların yazılması gerekmektedir.

Bilişim yönlendirici: 192.168.0.0 / 192.168.1.0 / 192.168.2.1

Elektronik yönlendiricisi: 192.168.0.0 / 192.168.3.1

![image3.22](/images/level_3/3_21.png) 

_Şekil-13_

•	Bil1 cihazı masaüstünde “Command Prompt” aracını kullanarak Bil2 ve Bil cihazları ile olan bağlantıyı kontrol edilmesi. 

![image3.23](/images/level_3/3_22.png) 

![image3.24](/images/level_3/3_23.png) 

_Şekil-14_



_**NUR TEMİZ**_
