### UYGULAMA

_Bu dökümanda oluşturulan ağ simülasyonu çalıştırılabilir pkt dosyasına [buradan](https://github.com/nurtemiz/network-lab/blob/master/pkt-files) ulaşabilirsiniz._

İki farklı yönlendiricinin bulunduğu Resim5.1’de gösterilen ağın cisco paket tracer ağ ortamında adım adım gerçeklenmesi.

![image5.1](/images/level_pro/5-1.png)

_Resim5.1 Ağın genel yapısı_

**1.	Ağ topolojisi için kullanılacak olan cihazlar simülasyon ortamına yerleştirilir ve aradaki bağlantılar yapılır.**

- **Yölendirici – Yönlendirici Bağlantısı**: Yerel ağda bağlantı için ethernet kabloları kullanılır. Bir yönlendirici yerel ağ bağlanırken “Ethernet” (veya Fast Ethernet) portundan bağlantı yapılır. Fakat yerel ağın dışına çıkarken yönlendiricilerin “Ethernet” portları kullanılmaz. Yönlendiriciler birbirine bağlanırken seri port (Serial Port) kullanılır. 

Seri portla birbirine bağlı iki yönlendirici üzerinde, mantıksal bir ayrım yapmak için kullanılan bir yapıdır. Seri porttan haberleşen cihazlarda bir tarafın DCE (Data Communications Equipment) diğer tarafında DTE (Data Terminal Equipment) olması gerekir.

Yönlendirici yapılandırmasında iki yönlendirici arasında veri iletim hızının belirlenmesi gerekir. DCE olan taraf, veri iletimindeki hızı belirleyen taraftır. DTE olan taraf ise belirlenen hızda veri iletimine katılan hısımdır.

Ağ simülasyon yazılımında yönlendiriciler çalışma alanına eklendiklerinde üzerlerinde seri port bulunmaz. Bunun için yönlendirici üzerinde çift tıklayarak yönlendirici yönetim penceresinde Fiziksel (Physical) sekmesinde, seri port eklemek gerekmektedir. Bu işlem için önce yönlendirici güç (power) tuşu kapatılır ve ardından WIC-2T modülü sürükle bırak yöntemiyle boş bir yuvaya takılır.

- **Anahtar – Yönlendirici Bağlantısı**:  Yönlendiricinin üzerinde, “FastEthernet” portlarından birine bağlantı yapıldı ve anahtar üzerinde de boşta olan bir porta bağlantı yapıldı. İletişimin başlaması için kapalı olan yönlendirici portlarının açılması ve yapılandırılması gerekmektedir.

Kapalı olan yönlendirici portlarını açmak için ayar (config) sekmesinde “FastEthernet” bölümü seçilir ve sağ tarafta “Port Status” bölümü açık (ON) konumuna getirilir.

- **AccesPoint Bağlantıları**: Program içinde erişim noktası, piyasada bulunabilecek sıradan tek portlu bir cihazı modellediğinden fiziksel (Physical) sekmesinde 10/100/1000 Mbit hızlarında bakır kablo veya 100/1000 Mbit hızları için fiber optik kablo bağlantılarının modüllerini barındırmaktadır. Ayar (Config) sekmesinde ise Port0 yerel ağ için Port1 kablosuz bağlantı için olmak üzere temel iki ayar noktası bulunmaktadır. Örneğin Port1 yapılandırılırken kablosuz ağ adı ve erişim noktasına bağlanacak olan cihazlar için erişim türü ve şifrenin belirlenmesi yeterli olacaktır.

- **PC - AccesPoint Bağlantısı**: Çalışma alanına eklenmiş olan bir bilgisayarın kablosuz bağlantısının kurulabilmesi için bilgisayarda Wireless Router modülünün takılmış olması gerekmektedir. Bu modül takılıp bilgisayar çalışır duruma geldikten sonra masaüstü sekmesinden PC wireless programını kullanarak yapılandırma işlemini gerçekleştirilir.


**2.	Bağlantılar kurulduktan sonra ağın simülasyonunun gerçeklenebilmesi için cihazların yapılandırılması gerekir.**

- **AccesPoint Bağlantı Ayarları**: Erişim noktasının yapılandırması işleminde kablosuz ağın yayın yaptığı port1 üzerinde kablosuz ağ yayın adı (SSID) isteğe bağlı olarak belirlendikten sonra erişim türü WPA2-PSK seçilmiş ve yine isteğe bağlı bir şifre tanımlanmalıdır.

- **AccesPoint Yapılandırılması**: Dizüstü bilgisayarın masaüstü sekmesinde bulunan PC Wireless programı çalıştırılır.

PC Wireless programının Connect sekmesine geçip birkaç saniye beklendiğinde erişim noktasının yayın ismi ekranda görünecektir. Çalışma alanında birden fazla erişim noktası yayın yapıyor olsaydı bunlardan birini seçip Connect düşmesine tıklamamız gerekirdi.

Kablosuz ağa bağlanacak cihaz için gerekli yapılandırma işlemleri tamamlanınca ekranda yeni bir pencere belirir. Bu pencerede seçilen erişim noktası yayınına bağlanmak için belirtilen türdeki erişim türü için geçerli parolayı girmemiz ve tekrar Connect düğmesine basmamız gerekmektedir.

- **Yönlendirici yapılandırması**: Yönlendiriciler yapılandırılırken hem yerel ağa bağlı olan hem de dış ağlara bağlı olan portlarının yapılandırılması gerekmektedir. 

Yönlendirme işlemi; temelde her yönlendiricinin kendisine bağlı bulunan diğer ağlarının bilgilerini, başka yönlendiricilerle paylaşmasıdır. Bu, farklı protokollerle gerçekleşebilir.

Bu aşamada yönlendiriciler için tasarlanmış olan RIP yönlendirme protokolünün yapılandırmak için bağlı bulunan ip adresleri bu alana eklenir.

- **PC Yapılandırması**: PC yapılandırması işlemi, bilgisayara TCP parametrelerinin (IP adresi, alt ağ maskesi, varsayılan ağ geçidi) atanması işlemidir. Bilgisayarların iletişim kurabilmeleri için paketlerin yerel ağın dışında dolaşabilmesi gerekmektedir. Bu işlemi yönlendiriciler gerçekleştirecektir.

## UYGULAMA ADIMLARI

- Çalışma alanına iki yönlendirici, bir accespoint, bir dağıtıcı, bir switch ve üç bilgisayar yerleştirildi ve tüm cihazlar föyde verildiği gibi isimlendirildi.

![image5.2](/images/level_pro/5-2.png)

_Resim5.2 Cihazların yerleştirilmesi_

- MEB ve Megep yönlendiricilerinin birbirine bağlamak için Seri (Serial) port takıldı. (Yönlendirici yönetim penceresin Fiziksel sekmesinde bulunan WIC-1T modülü kullanıldı.)

![image5.3](/images/level_pro/5-3.png) 
![image5.4](/images/level_pro/5-4.png)

_Resim5.3 Router’lara WIC-1T modülünün takılması_

-	MEB yönlendiricisi diğer cihazlara bağlandı. MEB yönlendiricisinin S0/1/0 portu Megep yönlendiricisinin S0/1/0 portuna, FA0/0 portu Yerel Ağ anahtarına bağlandı ve MEB yönlendiricisinin portlarına IP atması yapıldı.

_S0/1/0 IP No: 192.168.0.1 Ağ maskesi: 255.255.255.0_

_FA0/0 IP No: 192.168.1.1 Ağ maskesi: 255.255.255.0_

![image5.5](/images/level_pro/5-5.png) 

![image5.6](/images/level_pro/5-6.png)   

_Resim5.4 MEB router yapılandırılması ve ip atamaları_

-	Megep yönlendiricisi diğer cihazlara bağlandı. Megep yönlendiricisinin S0/1/0 portu MEB yönlendiricisini S0/1/0 portuna FA0/0 portu Hub0 dağıtıcısına bağlandı ve MEGEP yönlendiricisinin portlarına IP atması yapıldı.

_S0/1/0 IP No: 192.168.0.2 Ağ maskesi: 255.255.255.0_

_FA0/0 IP No: 192.168.2.1 Ağ maskesi: 255.255.255.0_

![image5.7](/images/level_pro/5-7.png) 

![image5.8](/images/level_pro/5-8.png) 

_Resim5.5 Megep router yapılandırılması ve ip atamaları_

-	Erişim noktası olan Kablosuz Ağ Erişim Noktası isimli accesspoint’in kablosuz ağ ortamında hizmet verebileceği şekilde yapılandırılması:

_Kablosuz Ağ Erişim Noktası için; SSID: MEGEP, WPA2-PSK: megep-bilisim_
 
![image5.9](/images/level_pro/5-9.png) 

_Resim5.6 Kablosuz Ağ Erişim Noktasının yapılandırılması_

•	Bil3 dizüstü bilgisayarını kablosuz ağa bağlamak için gerekli düzenlemelerin yapılması:

Bil dizüstü bilgisayarın yönetim penceresi fiziksel (Physical) sekmesinde, bilgisayarın kapatılmasının, ardından bilgisayarda takılı olan Ethernet kartını çıkartılması ve yerine Wireless Router modülünü takılması.

![image5.10](/images/level_pro/5-10.png) 

_Resim5.7 Dizüstü PC’den Ethernet kartının çıkartılması_

![image5.11](/images/level_pro/5-11.png) 

_Resim5.8 Kablosuz Ağ Erişim Noktasının yapılandırılması_

-	Dizüstü bilgisayarların kablosuz ağa bağlamak için yapılandırılması:

Bu işlem için dizüstü bilgisayarların masaüstünde PC Pireless yardımcı programı kullanılır. SSID seçimi yapılarak, erişim şifreleri kullanılır.

![image5.12](/images/level_pro/5-12.png)  

_Resim5.9 Pc – Kablosuz bağlantı yapılandırılması_

![image5.14](/images/level_pro/5-14.png)

![image5.15](/images/level_pro/5-15.png) 

_Resim5.10 Pc – Kablosuz bağlantı yapılandırılması_

-	Masaüstü ve dizüstü bilgisayarlar için IP tanımlamasının yapılması:

_Bil1 için: IP No: 192.168.1.10, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.1.1_

_Bil2 için: IP No: 192.168.1.11, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.1.1_

_Bil için: IP No: 192.168.2.10, Ağ maskesi: 255.255.255.0, Ağ Geçidi: 192.168.2.1_

![image5.16](/images/level_pro/5-16.png) 

_Resim5.11 Pc yapılandırılması_

-	Yönlendiricilerin yönlendirme bilgilerini güncellemek için dinamik yönlendirme işlemini geçekleştirilmesi.

(Yönlendirici yönetim penceresinde ayarlar (Config) sekmesinde RIP bölümüne seçili yönlendiricinin bağlı bulunduğu ağların yazılması gerekmektedir.

_MEB yönlendirici: 192.168.0.0 / 192.168.1.0 / 192.168.2.0_

_Megep yönlendiricisi: 192.168.0.0 / 192.168.2.0 / 192.168.1.0_

![image5.17](/images/level_pro/5-17.png)    
![image5.18](/images/level_pro/5-18.png)

_Resim5.12 Router yönlendirme yapılandırılması_

-	Ağın test edilmesi:
 
![image5.19](/images/level_pro/5-19.png)    
![image5.20](/images/level_pro/5-20.png)

_Resim5.13 Ağın test edilmesi_

_**NUR TEMİZ**_



