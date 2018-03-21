### WAN SİMÜLASYONU

![image3.1](/images/level_3/3_24.png)

1. WAN Cihazları

1.1. Wide Area Network (WAN)

Büyük bir coğrafi alana yayılmış bilgisayar ağına WAN-Geniş Alan Ağı denir. Diğer bir deyişle bir WAN, iki veya daha fazla yerel alan ağının [Local Area Network-LAN] birleştirilmiş halidir. Farklı yerel alan ağlarının haberleşmesidir. Çoğunlukla public network olarak isimlendirilen telefon şebekesi, ATM, Frame Relay, uydu, kiralık hatlar, TDM üzerinden oluşturulurlar. Dünyadaki en büyük WAN, Internet'tir.

1.2. WAN Cihazları

•	ADSL Modem
•	Yönlendirici (router)

2. Yönlendirici – Yönlendirici Bağlantısı

Yerel ağda bağlantı için ethernet kabloları kullanılır. Bir yönlendirici yerel ağ bağlanırken “Ethernet” (veya Fast Ethernet) portundan bağlantı yapılır. Fakat yerel ağın dışına çıkarken yönlendiricilerin “Ethernet” portları kullanılmaz. Yönlendiriciler birbirine bağlanırken seri port (Serial Port) kullanılır. Aşağıdaki resimde bir seri kablo görülmektedir. Bu kabloda ince olan sol kısım, yönlendiriciye bağlantı yapmak için kullanılır. Sağ tarafta bulunan kısım ise başka bir yönlendiriciden gelen başka bir seri kablo ile bağlanır.

3. DCE ve DTE Bağlantıları

Seri portla birbirine bağlı iki yönlendirici üzerinde, mantıksal bir ayrım yapmak için kullanılan bir yapıdır. Seri porttan haberleşen cihazlarda bir tarafın DCE (Data Communications Equipment) diğer tarafında DTE (Data Terminal Equipment) olması gerekir. Yönlendirici yapılandırmasında iki yönlendirici arasında veri iletim hızının belirlenmesi gerekir. DCE olan taraf, veri iletimindeki hızı belirleyen taraftır. DTE olan taraf ise belirlenen hızda veri iletimine katılan hısımdır.
    
_Şekil-1 Yönlendiriciye seri port modülü ekleme_


![image3.1](/images/level_3/3_1.png)
