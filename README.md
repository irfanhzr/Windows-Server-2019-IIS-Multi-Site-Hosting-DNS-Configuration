# Windows-Server-2019-IIS-Multi-Site-Hosting-DNS-Configuration
Bu proje, sanallaştırma ortamında Windows Server 2019 altyapısı kurularak; Active Directory (AD), DNS ve IIS (Internet Information Services) rollerinin yapılandırılmasını içermektedir. Tek bir sunucu üzerinde IP tabanlı ve Host Header (Alan Adı) tabanlı yönlendirmelerle birden fazla web sitesi (Virtual Hosting) başarıyla yayınlanmıştır.
Bu proje, sanallaştırma ortamında Windows Server 2019 altyapısı kurularak; Active Directory (AD), DNS ve IIS (Internet Information Services) rollerinin yapılandırılmasını içermektedir. Tek bir sunucu üzerinde IP tabanlı ve Host Header (Alan Adı) tabanlı yönlendirmelerle birden fazla web sitesi (Virtual Hosting) başarıyla yayınlanmıştır.

🛠️ Kullanılan Teknolojiler ve Araçlar
Sanallaştırma: VMware Workstation 17.5

İşletim Sistemi: Windows Server 2019

Sunucu Rolleri: Active Directory Domain Services (AD DS), DNS Server, IIS (Web Server)

Ağ Yapılandırması: Custom Virtual Network (VMnet2), Statik IP Yapılandırması

⚙️ Gerçekleştirilen Teknik Adımlar
1. Sanal Sunucu Kurulumu:

VMware Workstation üzerinde Windows Server 2019 kurulumu gerçekleştirildi.

Donanım sanallaştırma ayarları (2 vCPU, 2GB RAM, 60GB Disk) optimize edildi.

Özel Ağ (VMnet2): İzole bir ağ ortamı oluşturularak sunucu ve istemci iletişimi yapılandırıldı.

2. Active Directory ve DNS Yönetimi:

ihazir.com domain yapısı ("Forest") oluşturuldu.

DNS Yönetimi (Forward Lookup Zones): Web siteleri için gerekli olan A (Host) kayıtları girildi.

www.ihazir.com -> 192.168.1.10

www.irfancan.com -> 192.168.1.10

www.canirfancan.com -> 192.168.1.10

3. IIS ile Çoklu Web Sitesi Yayını (Multi-Site Hosting):

IIS Yöneticisi üzerinde farklı dizinlere ("Physical Path") sahip 4 farklı web sitesi oluşturuldu.

Site Bindings (Bağlamalar): Her site için Host Header tanımlamaları yapıldı. Bu sayede tek bir IP adresi (192.168.1.10) üzerinden gelen istekler, alan adına göre doğru web sitesine yönlendirildi.

Site 1: asfa (www.ihazir.com)

Site 2: web2 (www.irfancan.com)

Site 3: web3 (www.canirfan.com)

Site 4: web4 (www.canirfancan.com)

4. Test ve Doğrulama:

İstemci üzerinden yapılan ping testleri ile DNS çözümlemesinin (Resolution) başarılı olduğu doğrulandı.
Web tarayıcısı üzerinden alan adlarına gidilerek her sitenin kendi özel içerik sayfasını sunduğu test edildi (Ekran görüntülerinde mevcuttur).
