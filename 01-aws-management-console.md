ENG
Navigating the AWS Management Console: Foundations
This module covers the core fundamentals of accessing, configuring, and optimizing your workflow within the Amazon Web Services (AWS) Cloud infrastructure using the AWS Management Console.

1. Setting Up Your AWS Account
To initiate cloud operations, establishing a properly configured AWS account with adherence to the AWS Free Tier guidelines is required.

AWS Free Tier Access: AWS offers a 12-month free tier for hands-on experience with core cloud infrastructure components.

Best Practices for Setup:

Secure the Root Account immediately using Multi-Factor Authentication (MFA).

Avoid deploying production workloads or routine daily tasks under the Root account; create isolated IAM users/roles instead.

Useful Resources:
AWS Free Tier Overview – Detailed catalog of always-free, 12-month free, and short-term trial services.

2. Launching and Customizing the AWS Management Console
The AWS Management Console is a web-based graphical user interface (GUI) designed for managing AWS services, monitoring cloud resource utilization, and handling billing infrastructure.

Unified Search: The console's central search bar allows rapid discovery of AWS services, documentation, features, and marketplace solutions.

Console Home Layout: A customizable dashboard featuring widgets for recent services, AWS Health metrics, cost management, and automated tutorials.

Customizing the Navigation Bar:
Efficiency in cloud administration relies on reducing navigation friction. You can optimize your workspace by managing service shortcuts directly on the top navigation bar.

Adding Shortcuts: Pin your most frequently accessed infrastructure components (e.g., EC2, S3, RDS) to the top bar.

Removing/Reordering: Drag, drop, or remove service icons to keep the navigation view clean and aligned with current project requirements.

Useful Resources:
AWS Management Console Portal – Official entry point for console operations.

AWS Console FAQs – Technical queries regarding console behavior, regional availability, and browser support.

Documentation: Using Search in AWS – Advanced tips on navigating via the global search interface.

Documentation: Customizing Shortcuts – Step-by-step instructions on personalizing the navigation bar interface.

3. Core Features & Interaction Paradigms
Interacting with the AWS ecosystem spans multiple modalities depending on automation requirements and infrastructure complexity.

Feature / Tool,Primary Use Case,Key Benefit
AWS Management Console (GUI),"Visual resource management, initial configuration, and monitoring.","User-friendly, low barrier to entry, ideal for quick inspections."
AWS CloudShell,Direct browser-based command-line access.,Pre-authenticated CLI environment without local installations.
Console Mobile Application,On-the-go monitoring and incident response.,Secure access to dashboards and basic operational status from mobile devices.

Useful Resources:
AWS Console Features – Deep dive into CloudShell integration, settings persistence, and account management capabilities.

TR

AWS Yönetim Konsolunda Gezinme: Temeller
Bu modül, Amazon Web Services (AWS) Bulut altyapısına AWS Yönetim Konsolu'nu kullanarak erişim sağlama, konsolu yapılandırma ve iş akışlarını optimize etme konularındaki temel prensipleri kapsamaktadır.

1. AWS Hesabının Kurulumu
Bulut operasyonlarını başlatmak için, AWS Ücretsiz Dağıtım (Free Tier) yönergelerine uygun olarak düzgün yapılandırılmış bir AWS hesabı oluşturulması gerekir.

AWS Free Tier Erişimi: AWS, temel bulut altyapı bileşenleriyle pratik deneyim kazanılması amacıyla 12 aylık bir ücretsiz kullanım katmanı sunar.

Kurulum İçin En İyi Pratikler (Best Practices):

Kök Hesabı (Root Account) çok faktörlü kimlik doğrulama (MFA) ile hemen güvence altına alınmalıdır.

Günlük rutin işler veya canlı ortam (production) iş yükleri için Kök Hesabı kullanılmamalı; bunun yerine izole edilmiş IAM kullanıcıları veya rolleri oluşturulmalıdır.

Faydalı Kaynaklar:
AWS Free Tier Genel Bakış – Sürekli ücretsiz, 12 ay ücretsiz ve kısa süreli deneme sunan servislerin detaylı kataloğu.

2. AWS Yönetim Konsolunu Başlatma ve Özelleştirme
AWS Yönetim Konsolu; AWS servislerini yönetmek, bulut kaynaklarının kullanımını izlemek ve faturalandırma altyapısını takip etmek için tasarlanmış web tabanlı bir grafik kullanıcı arayüzüdür (GUI).

Merkezi Arama (Unified Search): Konsolun üst kısmında yer alan arama çubuğu; AWS servislerinin, teknik dokümantasyonların, özelliklerin ve pazaryeri (marketplace) çözümlerinin hızla bulunmasını sağlar.

Konsol Ana Sayfa Düzeni: En son kullanılan servisler, AWS Sağlık (Health) metrikleri, maliyet yönetimi ve otomatik kılavuzlar gibi bileşenleri (widget) içeren, özelleştirilebilir bir kontrol panelidir.

Gezinme Çubuğunu Özelleştirme:
Bulut yönetiminde verimlilik, menüler arasındaki gezinme süresini azaltmaya bağlıdır. En sık kullanılan servis kısayollarını doğrudan üst gezinme çubuğuna sabitleyerek çalışma alanınızı optimize edebilirsiniz.

Kısayol Ekleme: En sık eriştiğiniz altyapı bileşenlerini (örneğin EC2, S3, RDS) üst çubuğa iğneleyebilirsiniz.

Kaldırma ve Yeniden Sıralama: Gezinme görünümünü temiz tutmak ve mevcut proje gereksinimlerine uygun hale getirmek için servis simgelerini sürükleyip bırakabilir veya kaldırabilirsiniz.

Faydalı Kaynaklar:
AWS Yönetim Konsolu Portalı – Konsol operasyonları için resmi giriş noktası.

AWS Konsolu SSS (Sıkça Sorulan Sorular) – Konsol davranışları, bölgesel kullanılabilirlik ve tarayıcı desteğine ilişkin teknik sorular.

Dokümantasyon: AWS'de Aramayı Kullanma – Global arama arayüzü üzerinden gezinmeye yönelik gelişmiş ipuçları.

Dokümantasyon: Kısayolları Özelleştirme – Gezinme çubuğu arayüzünü kişiselleştirmeye yönelik adım adım talimatlar.

3. Temel Özellikler ve Etkileşim Yöntemleri
AWS ekosistemiyle etkileşim kurmak, otomasyon gereksinimlerine ve altyapı karmaşıklığına bağlı olarak birden fazla yöntemle gerçekleştirilebilir.

Özellik / Araç,Temel Kullanım Senaryosu,En Belirgin Avantajı
AWS Yönetim Konsolu (GUI),"Görsel kaynak yönetimi, ilk yapılandırmalar ve izleme.","Kullanıcı dostudur, öğrenme eğrisi düşüktür; hızlı kontroller için idealdir."
AWS CloudShell,Doğrudan tarayıcı tabanlı komut satırı erişimi.,"Yerel bilgisayara kurulum gerektirmeyen, önceden kimlik doğrulaması yapılmış hazır CLI ortamı."
Konsol Mobil Uygulaması,Hareket halindeyken izleme ve olaylara müdahale (incident response).,Mobil cihazlardan panellere ve temel operasyonel durumlara güvenli erişim.

Faydalı Kaynaklar:
AWS Konsol Özellikleri – CloudShell entegrasyonu, kalıcı ayarlar ve hesap yönetimi yeteneklerine derinlemesine bakış.
