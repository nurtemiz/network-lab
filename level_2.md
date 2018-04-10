### 1.	LAN SİMULASYONU

_Bu dökümanda oluşturulan ağ simülasyonu çalıştırılabilir pkt dosyasına [buradan](https://github.com/nurtemiz/network-lab/blob/master/pkt-files) ulaşabilirsiniz._

![image2.1](/images/level_2/image2_1.png)

#### 1.1	LAN Cihazları

LAN (Local Area Network), fiziksel olarak birbirine yakın olan bilgisayarların arasında bir ağ bağlantısı kurmak amacıyla tercih edilen bağlantı şeklidir. 

Bir yerel ağ tasarımı yapılırken ağda masaüstü ve dizüstü bilgisayarlar bulunur. Bilgisayarların birbirleriyle bağlantı kurup yerel ağda haberleşme yapabilmeleri için dağıtıcı (hub) veya anahtar (switch) gibi ağ iletişim cihazlarının bulunması gerekir.

#### 1.2	Switch-Router Bağlantısı 

•	Föy-1’de de bahsedildiği gibi çalışma alanına cihaz eklemek için, ağ cihazlarının bulunduğu sol panelden bir cihaz türü seçilir ve sürükle-bırak yöntemiyle çalışma alanına yerleştirilir. Föy-2 de bir router ve bir switch üzerinden örnek çalışma yapıldığından, bir switch ve router çalışma alanına eklenir. (Birden fazla cihaz eklemek için ctrl tuşuna basılı tutmak yeterli olacaktır.)

•	Çalışma alanına yerleştirilen bu iki cihaz arasındaki bağlantı için düz bakır kablo (Copper Straight- Through) kullanılır. Ya da bağlantı türünü otomatik belirle (Automatic Choose Connection Type) seçerek de bağlantı yapılabilir.

•	İki cihaz birbirine bağlandığında aradaki kablonun kırmızı olduğu görülür. Bunun nedeni router-ların tüm portlarının default olarak kapalı olmasıdır. Kapalı olan router portlarını açmak için router-a çift tıklanır ve açılan pencerede config sekmesinde -FastEthernet 0/0 -bölümü seçilir ve -Port status- bölümü de -ON- olarak değiştirilir. Ya da router işletim sistemi (IOS) komutları ile de aynı işlem gerçekleştirilir.

#### 1.3	PC – Switch Bağlantısı 

•	Çalışma alanına bir PC ve bir anahtar eklenir.

•	PC ile anahtar arasında düz kablo kullanılır bağlantılar bölümünden düz kablo seçilerek aradaki bağlantı için önce switch üzerinde boş bir port seçilir. Ardından bağlantının PC’ye aktarılması için PC seçilir. PC üzerinde seri port ve hızlı “Ethernet” bağlantısı bulunmaktadır. Bilgisayar yerel ağa “Ethernet” portundan bağlanacağı için “FastEthernet” seçilmelidir.

•	Bilgisayar ve anahtar üzerinde yanan yeşil ışıklar, bağlantının hatasız bir şekilde yapıldığını göstermektedir. Eğer düz bakır kablo yerine çapraz (Cross) kablo kullanılsaydı kabloların uçlarında kırmızı ışık yanardı. Bunun anlamı, bağlantı olmasına rağmen veri iletimi sağlanamıyor olmasıdır.

#### 1.4	PC Yapılandırması

•	PC yapılandırması, bilgisayara TCP parametrelerinin (IP adresi, alt ağ maskesi, varsayılan ağ geçidi) atanması işlemidir. 

•	PC çift tıklanarak açılan pencereden, Desktop -> Ip Configuration seçilir açılan yeni pencerede; IP address ve Subnet mask, bilgisayarın yerel ağda iletişim kurmak için kullanacağı TCP parametrelerini oluşturmaktadır. Default Gateway ise bilgisayarın, İnternet gibi dış ağlara erişebilmesi için yönlendirileceği cihazın IP numarasını göstermektedir. DNS Server ise bilgisayarın, web sayfalarına ulaşmak için alan adından IP sorgulamasının yapılacağı cihazın IP adresini göstermektedir.


#### 1.5	Router Konfigürasyonu

Yerel ağda çalışacak bir yönlendirici yapılandırılırken sadece “Ethernet” portları için yapılandırma işlemi gerçekleştirilir.

•	Router-a çift tıklanır ve açılan pencerede config sekmesinde -FastEthernet 0/0 -  portuna IP adresi ve alt ağ maskesi atması işlemi yapılırken -Port Status- kısmında bulunan –ON- onay kutusunun işaretlenerek portun iletime açılması gerekmektedir. 

•	Aynı işlemin yönlendiricinin -FastEthernet0/1- portu için de yapılması gerekmektedir. 

#### 1.6	Yönlendirme Yapılandırması

Yönlendiricinin yapılandırması işleminde temel olarak router-ın bilgisayarlar için yerel ağdan İnternete veya başka yerel ağlara ulaşmak için bir geçit yolu olacağının bilinmesi gerekir. Yönlendiricinin yerel ağa bağlı olan portundaki IP adresi, bilgisayarlar için ayarlandığı default gateway-i, IP adresi olması gerektiğini unutmamak gerekir. Föyde verilen örneği gerçekleyecek olursak; -MEGEP- isimli yönlendiricinin iki portunda iki yerel ağ bağlantısı bulunmaktadır. 

Örneğe göre -Router-ın Fa0/0 ayağına verilecek olan IP adresi 192.168.1.0/24 ağı için default gateway adresi olacaktır. Hatırlamakta kolaylık olması açısından, kullanılabilir ilk IP adresini vermekte fayda vardır. Bu örneğe göre Fa0/0 ayağına, 192.168.1.1 IP adresi default gateway olarak verilebilir.

![image2.2](/images/level_2/image2_2.png)

_Resim2.2 PC yapılandırması_

**Yönlendirici ağlar arasında paketlerin geçişini ve trafiğin denetlenmesini sağlayacağı için her iki portunda da yerel ağlarda kullanılan IP adresleri bulunması ve portların açık olması gerekmektedir.**

**Yönlendiricinin yapılandırması işleminde, yerel ağa bağlı bulunan “Ethernet” portlarını yapılandırılması gerekmektedir.**

**IP Address ve subnet mask bölümlerine, yönlendiricinin bilgisayarlar için varsayılan ağ geçidi (Default Gateway) olması gerektiği unutulmamalıdır.**

![image2.3](/images/level_2/image2_3.png)

_Resim2.3 Ip adres ataması (PC)_


![image2.4](/images/level_2/image2_4.png)


_Resim2.4 Router yapılandırılması_


Bütün bu işlemler uygulandıktan sonra örneğin son hali Resim2.5-de olduğu gibidir.

![image2.5](/images/level_2/image2_1.png)

_Resim2.5 Ağın son hali_

#### 1.7	Föyde Verilen Örnek İçin Test Aşamasının Gerçeklemesi

Yukarıdaki örnekteki ağın çalışıp çalışmadığını test etmek için iki yol bulunmaktadır. İlki Ogr1 bilgisayarının masaüstünde bulunan komut satırı (Command Prompt) programını çalıştırılmasıdır. Komut satırı arabiriminde, Ogr4 bilgisayarı ağ bağlantısının durumunu kontrol etmek için ping komutunu kullanırız. 

**Ping** komutu, ICMP (Internet Control Message Protokol) kapsamında yankı (Echo) paketleri gönderir. Eğer ulaşmak istediğimiz bilgisayar, yankı paketlerimize yanıt veriyorsa iki bilgisayar arasında bağlantı var demektir. Eğer bağlanmak istediğimiz bilgisayar, yanıt vermiyorsa bağlantı ile ilgili bir sorun var demektir. (Resim2.6-da ping işlemi gerçeklenmiştir.)

![image2.6](/images/level_2/image2_5.png)


_Resim2.6 Föy-de yapılması istenilen atamalar_

![image2.7](/images/level_2/image2_6.png)


_Resim2.7 Ağda bulunan farklı pc-lere ping atılması_

Ogr4 bilgisayarının IP numarası, 172.16.0.12 olduğu için ping komutunun yanında bu adres belirtilmişti. Komutun sonunda, komutla ilgili bilgi verilmektedir. 4 paket gönderilmiş ve sadece 3 pakete yanıt alınabilmiş demektir. Bunun sebebi, gönderilen ilk paket, ARP işlemi için kullanıldığından bu paket için bir yanıt alınamamış olmasıdır. Bu durum ekranda request timeout (istek zaman aşımına uğradı) satırında belirtilmektedir.

Bağlantının test edilmesinin bir diğer yolu da simülasyon (simulation) çalışma modunda ağın test edilmesidir. Simülasyon moduna geçildiği zaman, çalışma alanının sağ tarafında yeni bir menü çıkar.

![image2.8](/images/level_2/image2_9.png)


_Resim2.8 Simulation menüsü_

Bu menü, üç bölümden oluşmaktadır. Bunlar; Event List, Play Control ve Event List Filter bölümleridir. Event List bölümünde, veri iletimi süresince gönderilen paketler listelenir. Play kontrol bölümüyse simülasyonun çalıştırılması ile ilgili olan kısımdır. Event List Filter bölümü, ağ simülasyonunda hangi protokollerin kullanılacağının belirlendiği bölümdür. Ağ simülasyon yazılımı, tüm protokolleri destekler ve ayrıca burada simülasyonda görmek istediğimiz protokolü seçebiliriz. 

Basit bir test için Event List Filter bölümünde bulunan Edit Filter düğmesine basarak sadece ICMP ile ARP protokollerinin seçilir. Burada tüm protokollerin seçili olması Simpel PDU yapısı açısından bir sıkıntı oluşturmaz. Simple PDU temelde ICMP ve ARP protokolleri ile çalışır. Yalnız simülasyon testi bu iki protokolle çalışsa bile seçili tüm protokoller için paket gönderme işlemi bitmeden test bitmiş olmaz. Bu da hem zaman kaybına hem de karışıklığa neden olacaktır.

![image2.9](/images/level_2/image2_8.png)

_Resim2.9 Event List Filter menusunde ARP ve ICMP protokollerinin seçilmesi_

Play Control bölümünde bulunan yatay kaydırma çubuğu, paketlerin ağ cihazları arasında gönderim hızını belirlemek için kullanır. Add Simple PDU bölümü ise ağ Event List Filter bölümünde bulunan protokoller için bir ağ simülasyonu yapmaya olanak tanır.
Add Simple PDU düğmesi seçili konumdayken ağ iletişiminin test edileceği Ogr1 bilgisayarına bastıktan sonra Ogr4 bilgisayarlarına basalım. Bu işlem sonucunda Şekil1.7.5’de görünen yapı ile karşılaşırız.

Ogr1 bilgisayarının üzerinde bir zarf görüntülenir ve ekranın sağ kısmında Ogr1 ile Ogr4 arasında bir veri trafiğinin gerçekleşeceği, bilgisi görüntülenir. Auto Capture/Play tuşuna bastığımızda simülasyon, ağ cihazları arasında paket gönderimini gösteren bir animasyon etkinliğinde gerçekleşir.

Simülasyon tamamlandıktan sonra Evenlt List bölümünde bulunan paketler incelenerek ağ iletişimi süresince, hangi olayların meydana geldiği analiz edilebilir.

### UYGULAMA FAALİYETİ

Yukarıda ki adımlar izlenerek uygulama faaliyetinin adım adım gerçekleştirilmesi aşağıdaki resimlerle gösterilmiştir.

![image2.11](/images/level_2/image2_10.png)


_Resim2.11 Ağın föyde belirtildiği gibi kurulması_


•	Sırasıyla bilgisayarlara IP adresi verildi.

(Bil1 -> IP address: 192.168.1.11, Subnet mask: 255.255.255.0, Default gateway:192.168.1.1,

Bil2 -> IP address: 192.168.1.12, Subnet mask: 255.255.255.0, Default gateway:192.168.1.1,

Bil3 -> IP address: 192.168.1.13, Subnet mask: 255.255.255.0, Default gateway:192.168.1.1,

Bil4 -> IP adres: 172.168.0.11, Subnet mask: 255.255.0.0, Default gateway: 172.168.0.1,

Bil5 -> IP adres: 172.168.0.12, Subnet mask: 255.255.0.0, Default gateway: 172.168.0.1,

Bil6 -> IP adres: 172.168.0.13, Subnet mask: 255.255.0.0, Default gateway: 172.168.0.1)


![image2.12](/images/level_2/image2_12.png)

![image2.13](/images/level_2/image2_11.png)


_Resim2.12 Föyde belirtilen ip ve default gateway adreslerine gör bilgisayarların yapılandırılması_


•	Routher-ın “Ethernet” portları açılarak, IP yapılandırması gerçekleştirildi.

(FA0/0: IP address: 192.168.1.1, Subnet mask: 255.255.255.0,

FA0/1: IP address: 172.16.0.1, Subnet mask: 255.255. 0.0)

![image2.14](/images/level_2/image2_13.png)

![image2.15](/images/level_2/image2_14.png)


_Resim2.13 Router-ın yapılandırılması_


•	Bil1 isimli bilgisayardan Bil4, Bil5 ve Bil6 bilgisayarları arasındaki bağlantının test edilmesi.

![image2.16](/images/level_2/image2_15.png)

![image2.17](/images/level_2/image2_16.png)


_Resim2.14 Bilgisayarlar arasındaki bağlantıların test edilmesi._


•	Bilgisayarlar arasındaki bağlantının simulation çalışma kipi kullanılarak test edilmesi.

![image2.18](/images/level_2/image2_19.png)


_Resim2.15 Simulation sekmesine geçip “Edit Filter” sekmesine geçilmesi_


![image2.19](/images/level_2/image2_8.png)


_Resim2.16 ICMP ve ARP protokollerini seçilmesi ve simulation için ağın hazır hale gelmesi_


![image2.20](/images/level_2/image2_19.png)

![image2.21](/images/level_2/image2_20.png)


_Resim2.17 Simulation-un başlatılması ve paketin hareketi_


![image2.22](/images/level_2/image2_21.png)


_Resim2.18 Simulation-un bitmesi_


•	Simulation panel-de Event list sekmesinde her hangi bir event-a çift tıkladığımızda, paketin hangi OSI katmanından geçtiğini takip edebiliriz.

![image2.23](/images/level_2/image2_22.png)

![image2.24](/images/level_2/image2_23.png)

![image2.25](/images/level_2/image2_24.png)


_Resim2.19 Eventlist-teki ilk event-in incelenmesi_
