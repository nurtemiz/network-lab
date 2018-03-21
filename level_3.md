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
