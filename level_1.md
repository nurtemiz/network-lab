### 1. AĞ SİMÜLASYON PROGRAMLARI

Simülasyon, gerçek bir dünya süreci veya sisteminin işletilmesinin zaman üzerinden taklit edilmesidir (Banks ve Carson, 1984). Ağ simülasyonu, bir ağ ortamının bilgisayarda modellenmesi ve ağın fiziksel olarak kurulumu yapılmadan nasıl çalışacağının test edilmesi demektir. Bu test, TCP ve OSI referans modelini tüm detaylarıyla kapsayacak düzeyde olursa gerçek yaşamdaki ağların modellenmesinde herhangi bir sorunla karşılaşmadan başarıyla tamamlanabilir. 

Ağ simülasyon programlarının büyük bir çoğunluğu, ağ ürünleri geliştiren firmaların eğitim ve tasarım amacıyla kullandıkları programlardır. 
Bu bağlamda kullanılan açık ve kapalı kaynak olmak üzere bir çok ağ simülasyon programları bulunmaktadır. Bunlar;

* Açık kaynak yazılımlar: Georgia Tech Network Simulator (GTNetS), SSF-NET, ns-2
* Kapalı kaynak yazılımlar: Cisco Packet Tracer, QpNet, QualNet, Router.Sim

Föyde kullanılması istenen yazılım Cisco Packet Tracer yazılımıdır. Bu program network öğrenmek isteyen herkes için kullanışlı bir programdır. İstenirse gerçek ortam simüle edilebilmektedir. Zaten network cihazları genelde telnet ya da ssh ile konfigüre edildiklerinden gerçek ortama yakın bir çalışma ortamı sağlıyor diyebiliriz. Yazılım üzerinde bulunan cisco marka network cihazları ile bilgisayarlar konulup istenilen kablo ile fiziksel bağlantıları yapılarak, network cihazları ve bilgisayarlar üzerinde istenen konfigürasyon yapılabilmektedir. Yazılım üzerinde bulunan cisco cihazlara hangi modüllerin takılabildiği de bu yazılım üzerinden görülebilmekte ve simulasyon için istenen modül takılabilmektedir. Gerçek Cisco Routerlarda kullanılan komutlarla buradaki routerlarlada çalışabilirsiniz gerçeğe bire bir yakın olan bu program network uzmanları olmak için ideal programdır. 

#### 1.1 Cisco Packet Tracer Simülasyon Programının Kurulumu

Programın aşağıdaki linkten indirilip kurulması föyde belirtildiği gibi kurulum adımlarının takip edilmesi aşamasıdır. Kurulum yapılırken föyden farklı olarak, yapılan çalışmaların kaydedildiği doysa yolu otomatik olarak belgeler klasörü olarak geldi bu yüzden kayıt yeri user kullanıcı klasörü olarak değiştirildi.
https://www.netacad.com/courses/packet-tracer-download/ 

#### 2.1 Cisco Packet Tracer Simülasyon Programının Genel Görünümü ve Menüler

* File menüsü: yeni proje açmak, mevcut projeyi açmak, projeyi kaydetme, projeyi yazdırmak gibi işlemler için kullanılır. (Eğer program tutorial-ları ile indirildiyse örnek bir proje de açılabilir.)

* Edit menüsü: seçili olan bir nesneyi kopyalama, yapıştırma, değişiklikleri ileri/geri alma gibi işlemler için kullanılır.

* Sol alt köşedeki menü, aktif cihazların eklenebildiği ikonlar ile gösterilen menü tasarımlarda ve çözümlemelerde en çok kullanılan menüdür. Bu menü aracılığı ile router, switch, hub, MLS (Multilayer Switch), bağlatı çeşidi (UTP, F/O, serial) eklemeleri seçimleri yapılabilir. Kullanılan cihazlar Cisco cihazlarıdır. Bunlara ek olarak custom cihaz tasarımı da yapılabilir ve mevcut cihaz menüden seçildikten sonra kart eklenerek tasarım kişiselleştirilebilir.

* Sağ alt köşeden Simulation seçilerek gerçek zamanlı gösterimden simülasyon gösterimine geçilir ve bir tasarımın hızlı bir şekilde simülasyonu yapılabilir. Ayrıca sağ taraftaki menüdeki tablardan devreler üzerinden gönderilen paketlerin tipleri seçilerek izledikleri yol ve cihazların davranışları simüle edilebilir. Bu tabın kullanımda sağladığı yarar yapılan bir tasarımın sahada uygulanmadan önce tepkilerini ölçmemize imkân sağlamasıdır.

* Sol üst köşeden Logical/Physical bölümünden, Physical seçilerek WAN ortamında yapılacak tasarımların uygulanmasında ya da yapılan büyük tasarımların daha geniş bir alanda görünümünü incelemek amacıyla kullanılır. Detaylardan uzaklaşarak tasarımın geniş görünümünü incelemek amacıyla kullanılır.

* Çalışma alanına bir network cihazı eklenmek istendiğinde sürükle-bırak şeklinde cihaz eklenir. Örneğin, bir router eklediğimizde ve bu router üzerine tıklandığında açılan pencerede bu router-ın detaylı özellikleri görüntülenmektedir. Physical bölümü router üzerinde değişiklik yapmak için kullanılır. Config bölümü router üzerinde komut ile yapılabilecek bazı değişikliklerin yapılabildiği yerdir. CLI bölümü, komut satırının görüntülendiği bölümdür. CLI tasarımlarda ve uygulamalarda en çok kullanılan kısımdır.


#### 2.	UYGULAMA

Föyde gerçeklemesi istenilen adımlar aşağıdaki gibidir. Bu adımlara göre gerçekleme yapılmıştır.

•	Ağ simülasyon yazılımını bilgisayara kurun.

-	Simülasyon programı yukarıda da bahsedildiği gibi kuruldu ve güncelleştirmeleri yapıldı, oturum açıldı.

•	Ağ simülasyon yazılımını çalıştırın.

•	Çalışma alanına bir dağıtıcı ekleyin.

-	Çalışma alanına bir network cihazının eklenmesi sürükle-bırak şeklinde yapılır. Bir dağıtıcı eklemek için sol alt köşede bulunan menüden Network Device seçildi ve alt menüden ise Hubs seçilerek bir hub çalışma alanına eklendi. Burada dağıtıcının modeli föyde verildiği gibi Hub-PT dir. Adı ise dağıtıcı olarak deriştirildi.

•	Çalışma alanına bir erişim noktası ekleyin.

-	Erişim noktası eklemek için yine sol alt menüden, Network Device -> Wireless Devices seçilerek bir AccesPoint-PT çalışma alanına eklendi ve föyde belirtildiği gibi adlandırıldı.

•	Çalışma alanına iki masaüstü iki dizüstü bilgisayar ekleyin.

-	Yine masaüstü bilgisayar ve dizüstü bilgisayar eklemek için, sol alt menüden bu sefer Netwrok Device yerine End Device seçildi ve iki masaüstü bilgisayar ve iki dizüstü bilgisayar çalışma alanına eklenerek adlandırıldı.

•	Dizüstü bilgisayarların ağ bağlantısı için “Ethernet” modülünü çıkartıp wireless modülünü takın.

-	Burada Ethernet modülünün değiştirilmesi işlemi için, dizüstü bilgisayarlara çift tıklanarak özelliklerinin görüntülenmesi sağlanır. Gelen pencerede Physical bölümünde öncelikle bilgisayarın power-off düğmesine basılır ve Ethernet modülü yine sürükle-bırak yapılarak bilgisayardan çıkarıldı. Boş olan modüle ise yine physical bölümünde sağla bulunan cihazlardan, föyde belirtildiği gibi, WPC300N modeli sürekle-bırak yapılarak boş olan modül yerine takıldı. Burada belirtilen WPC300N (Wireless-N Notebook Adapter), bir wireless modülüdür.

•	Çalışma alanına bir DSL Modem ekleyin.

-	DSL modem eklemek için Network Device -> Wan Emulation -> Dsl Modem seçilerek çalışma alanına eklendi ve adlandırıldı.

•	Çalışma alanına bir bulut ekleyin.

-	Bulut eklemek için ise Network Device -> Wan Emulation -> Cloud-PT seçildi ve adlandırıldı. 

•	Resimde görüldüğü şekilde cihazları bağlayın.

-	Eklenen cihazları birbirlerine bağlarken, hangi cihazlar arasında hangi bağlantının olması gerektiğinden emin olunmadığı için Automatically Choose Connection Type bağlantı türü seçildi.

•	Çalışmayı daha sonra yapılandırmak üzere kaydedin.

-	Kaydetmek için, File -> Save seçilerek dosya yolu verildi ve çalışma kaydedildi.
Yukarıdaki adımlar izlenerek ve yine föyde verilen öneriler dikkate alınarak istenilen ağ tasarımı gerçeklenmiş olup Resim 1.1-de gösterilmiştir.

![image1.1](/images/level_1/image1.1.png)
