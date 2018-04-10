### KABLOSUZ AĞ SİMÜLASYONU 

_Bu dökümanda oluşturulan ağ simülasyonu çalıştırılabilir pkt dosyasına [buradan](https://github.com/nurtemiz/network-lab/blob/master/pkt-files/foy_4.pkt) ulaşabilirsiniz._

![image4.1](/images/level_4/4-0.png)

**1.	Kablosuz Cihazlar**

Ağ simülasyon yazılımının içinde kablosuz ağ cihazı olarak, erişim noktası (Access Point) ve kablosuz modem (Wireless Router) bulunuyor.
Kablosuz cihazdan bahsedildiği zaman, masaüstü ve dizüstü bilgisayarlar için kullanılacak olan kablosuz ağ kartları düşünülmelidir. PC nesnesinde masaüstü ve dizüstü bilgisayarları için modüller (Modules) sekmesi altında iki seçenek bulunur. Bunlardan ilki Wireless Router, ikincisi de PT-HOST-NM-1W-A modülleridir. Bu iki modül arasında teknik bir fark olmamakla birlikte bu çalışmada programın test aşaması için Wireless Router modülü kullanacak. Bunun sebebi, bilgisayarda kablosuz ağa bağlantı yapmak için masaüstü sekmesinde bulunan PC-Wireless yazılımının sadece Wireless Router için hazırlanmış olmasıdır.

**1.1	Kablosuz Modem**

Kablosuz modem üzerine fare ile çift tıkladığınızda modem yapılandırmasının yer aldığı pencere görüntülenir. Kablosuz modem yapılandırması:

•	Kablosuz modem, fiziksel olarak eklenebilecek herhangi bir bileşene sahip olmadığından modüller (Modules) kısmı boş olarak görüntülenmektedir. 

•	Ayarlar (Config) sekmesinde modemin İnternet, yerel ağ ve kablosuz ağ için ayarlarının yapılabileceği bir bölüm yer almaktadır.

•	Grafiksel kullanıcı ara yüzü (GUI) sekmesindeyse modemi bir bilgisayara bağlayıp İnternet gezginiyle modeme bağlandığı zaman, gelen pencerede yönetim arayüzü görüntülenmektedir.

•	Ağ simülasyon yazılımının amacı WRT300N kablosuz modemini tanıtmak olmadığından Ayar (Config) sekmesini kullanarak modem yapılandırmasını gerçekleştirilecektir. Fakat istenilirse aynı işlemler GUI sekmesi kullanılarak da gerçekleştirilebilir.

**1.2	Erişim Noktası**

Program içinde erişim noktası, piyasada bulunabilecek sıradan tek portlu bir cihazı modellediğinden fiziksel (Physical) sekmesinde 10/100/1000 Mbit hızlarında bakır kablo veya 100/1000 Mbit hızları için fiber optik kablo bağlantılarının modüllerini barındırmaktadır.
Ayar (Config) sekmesinde ise Port0 yerel ağ için Port1 kablosuz bağlantı için olmak üzere temel iki ayar noktası bulunmaktadır.
Örneğin Port1 yapılandırılırken kablosuz ağ adı ve erişim noktasına bağlanacak olan cihazlar için erişim türü ve şifrenin belirlenmesi yeterli olacaktır. 

**1.3	PC Kablosuz Bağlantısı**

Çalışma alanına eklenmiş olan bir bilgisayarın kablosuz bağlantısının kurulabilmesi için bilgisayarda Wireless Router modülünün takılmış olması gerekmektedir. Bu modül takılıp bilgisayar çalışır duruma geldikten sonra masaüstü sekmesinden PC wireless programını kullanarak yapılandırma işlemini gerçekleştirin.

Çalışma alanında aşağıdaki senaryo kapsamında bir kablosuz ağ tasarımını gerçekleştirilirilecek olursa; bu ağda iki masaüstü ve iki dizüstü bilgisayar ile bir yönlendirici, bir dağıtıcı ve bir erişim noktası bulunmaktadır. Dağıtıcının yönlendirici ve bilgisayarlar ile arasında düz bakır kablo bağlantısı yapıldığını, erişim noktası ile yönlendirici arasında ise çapraz bakır kablo bağlantısı yapılacaktır. Dizüstü bilgisayarlar ile erişim noktasını bağlamak için herhangi bir kablo kullanılması mümkün değildir. Dizüstü bilgisayarlarda “Ethernet” modülünün çıkartılarak yerine Wireless Router modülünün takılmış olması bu durumu mümkün kılmıştır. 
Kablosuz ağın yapılandırma işlemine başlamadan önce yönlendiricinin ve bilgisayarlarının IP yapılandırmasının gerçeklenmesi gerekir. 

**2.	Kablosuz Cihaz Bağlantı Ayarları**

Erişim noktasının yapılandırması işleminde kablosuz ağın yayın yaptığı port1 üzerinde kablosuz ağ yayın adı (SSID) isteğe bağlı olarak belirlendikten sonra erişim türü WPA2-PSK seçilmiş ve yine isteğe bağlı bir şifre tanımlanmalıdır. 

**3.	Kablosuz Cihaz Ağ Ayarları**

Dizüstü bilgisayarın masaüstü sekmesinde bulunan PC Wireless programı çalıştırılır.

PC Wireless programının Connect sekmesine geçip birkaç saniye beklendiğinde erişim noktasının yayın ismi ekranda görünecektir. Çalışma alanında birden fazla erişim noktası yayın yapıyor olsaydı bunlardan birini seçip Connect düşmesine tıklamamız gerekirdi. 

**4.	Kablosuz Ağ Güvenlik Ayarları**

Kablosuz ağa bağlanacak cihaz için gerekli yapılandırma işlemleri tamamlanınca ekranda yeni bir pencere belirir. Bu pencerede seçilen erişim noktası yayınına bağlanmak için belirtilen türdeki erişim türü için geçerli parolayı girmemiz ve tekrar Connect düğmesine basmamız gerekmektedir. 

### UYGULAMA

**•	Çalışma alanına bir dağıtıcı, üç erişim noktası, üç dizüstü bilgisayar ve bir masaüstü bilgisayarın yerleştirilmesi:**

![image4.2](/images/level_4/4-1.png)
 
**•	Erişim noktalarının kablosuz ağ ortamında hizmet verebileceği şekilde yapılandırılması:**

_Bilişim isimli erişim noktası için; SSID: Bilisim, WPA2-PSK: bilisim1_

_MEB isimli erişim noktası için; SSID: MEB, WPA2-PSK: bilisim2_

_Megep isimli erişim noktası için; SSID: Megep, WPA2-PSK: bilisim3_
   
![image4.3](/images/level_4/4-2.png)

![image4.4](/images/level_4/4-3.png)

![image4.5](/images/level_4/4-4.png)

![image4.6](/images/level_4/4-5.png)


**•	Dizüstü bilgisayarları kablosuz ağa bağlamak için gerekli düzenlemelerin yapılması:**

Sırasıyla, dizüstü bilgisayarların yönetim penceresi fiziksel (Physical) sekmesinde, bilgisayarların kapatılmasının, ardından bilgisayarda takılı olan Ethernet kartını çıkartılması ve yerine Wireless Router modülünü takılması.

![image4.7](/images/level_4/4-6.png)

![image4.8](/images/level_4/4-7.png)
 
**•	Dizüstü bilgisayarların kablosuz ağa bağlamak için yapılandırılması:**

Her dizüstü bilgisayarı, karşısında bulunan erişim noktasını kullanılarak kablosuz ağa bağlanması. Bu işlem için dizüstü bilgisayarların masaüstünde PC wireless yardımcı programı kullanılır. SSID seçimi yapılarak, 2. basamakta belirtilen erişim şifreleri kullanılır.
  
![image4.9](/images/level_4/4-8.png)

![image4.10](/images/level_4/4-9.png)
 
![image4.11](/images/level_4/4-10.png) 

![image4.12](/images/level_4/4-11.png) 

![image4.13](/images/level_4/4-12.png) 

![image4.15](/images/level_4/4-14.png) 

![image4.16](/images/level_4/4-15.png) 

**•	Masaüstü ve dizüstü bilgisayarlar için IP tanımlamasının yapılması:**

_Laptop0 için; IP adres : 192.168.1.10, Ağ maskesi:255.255.255.0_

_Laptop1 için; IP adres : 192.168.1.11, Ağ maskesi:255.255.255.0_

_Laptop2 için; IP adres : 192.168.1.12, Ağ maskesi:255.255.255.0_

_PC0 için; IP adres : 192.168.1.13, Ağ maskesi:255.255.255.0_

![image4.17](/images/level_4/4-16.png) 

![image4.18](/images/level_4/4-17.png) 

![image4.19](/images/level_4/4-18.png) 

![image4.20](/images/level_4/4-19.png) 
  

**•	PC0 masaüstü bilgisayardan sırasıyla Laptop 0-1-2 ile olan bağlantıların ping komutu kullanarak test edilmesi:**

PC0 masaüstünde Command Prompt yardımcı programını açılarak komut satırını aşağıdaki komutların yazılması.

_> ping 192.168.1.10; > ping 192.168.1.11;  > ping 192.168.1.12;_

![image4.21](/images/level_4/4-21.png) 
 
**•	Laptop0 ile Laptop2 arasındaki bağlantının simulation kipinde tekrarlanması:**
  
![image4.22](/images/level_4/4-22.png) 

![image4.23](/images/level_4/4-23.png) 

**_NUR TEMİZ_**
