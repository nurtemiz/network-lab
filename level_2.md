### 1.	LAN SİMULASYONU

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

Yönlendiricinin yapılandırması işleminde temel olarak router-ın bilgisayarlar için yerel ağdan İnternete veya başka yerel ağlara ulaşmak için bir geçit yolu olacağının bilinmesi gerekir. Yönlendiricinin yerel ağa bağlı olan portundaki IP adresi, bilgisayarlar için ayarlandığı default gateway-i, IP adresi olması gerektiğini unutmamak gerekir. Föyde verilen örneği gerçekleyecek olursak; -MEGEP- isimli yönlendiricinin iki portunda iki yerel ağ bağlantısı bulunmaktadır. Örneğe göre -Router-ın Fa0/0 ayağına verilecek olan IP adresi 192.168.1.0/24 ağı için default gateway adresi olacaktır. Hatırlamakta kolaylık olması açısından, kullanılabilir ilk IP adresini vermekte fayda vardır. Bu örneğe göre Fa0/0 ayağına, 192.168.1.1 IP adresi default gateway olarak verilebilir.

