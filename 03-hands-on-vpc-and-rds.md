ENG

Harika bir noktaya geldik. 3. dosya reponun en önemli kırılım noktalarından biri çünkü işin içine ilk defa Hands-on Practice (Uygulamalı Pratik) ve temel mimari bileşenler (VPC ve RDS) giriyor.

İstediğiniz gibi resmi AWS dokümantasyon linklerini güncel şekilde bularak içeriğe gömdüm. Bu dosyanın adını sistematiği bozmamak için 03-hands-on-vpc-and-rds.md yapabilirsiniz.

İşte doğrudan repoya ekleyebileceğiniz, kurumsal standartlarda hazırlanmış İngilizce ve Türkçe sürümler:

Sürüm 1: İngilizce (Global/Kurumsal Format)
Module 03: Hands-On Practice – Core Networking & Managed Databases
This module focuses on practical infrastructure deployment by defining network isolation boundaries and provisioning managed database layers within the AWS ecosystem.

1. Understanding Core Infrastructure Components
Amazon Virtual Private Cloud (VPC)
An Amazon VPC is a logically isolated virtual network dedicated to your AWS account. It acts as your private data center within the cloud, granting you complete control over your networking environment.

Subnets: Segments of a VPC's IP address range.

Public Subnets: Connected to the internet via an Internet Gateway; used for user-facing resources (e.g., web servers).

Private Subnets: Isolated from direct internet access; used for backend logic and storage layers.

Security & Isolation: Traffic flow is controlled at the network level using Network Access Control Lists (NACLs) and at the instance level using Security Groups (stateful firewalls).

Amazon Relational Database Service (RDS)
Amazon RDS is a fully managed relational database service that simplifies provisioning, operating, and scaling industry-standard databases (such as PostgreSQL, MySQL, MariaDB, and SQL Server) in the cloud.

Automated Management: AWS handles time-consuming administrative tasks including hardware provisioning, database software patching, automated backups, and failure detection.

High Availability: Supports Multi-AZ deployments, which automatically replicate data synchronously to a standby instance in a different Availability Zone for seamless failover.

2. Hands-On Architectural Scenario: Secure Database Isolation
In production-grade cloud engineering, databases are never exposed directly to the public internet. The standard architecture places computing frontends in a public subnet while isolating the database layer inside a private subnet.

Practical Implementation Workflow:
Network Provisioning: Define a custom VPC and allocate distinct public and private subnet blocks across multiple Availability Zones.

Gateway Configuration: Attach an Internet Gateway (IGW) to enable public subnets to route traffic outbound to the internet.

Database Deployment: Launch an Amazon RDS instance, explicitly assigning it to the newly created private subnets.

Access Control (Firewalls): Configure an RDS Security Group that strictly allows inbound database traffic (e.g., port 5432 for PostgreSQL or 3306 for MySQL) only coming from the frontend application's security group.

3. Reference Documentation & Learning Links
Official AWS Guides:
Amazon VPC Overview & FAQs – Detailed breakdowns of cloud networking, subnets, and endpoint architectures.

Amazon VPC User Guide – Official technical documentation for configuring virtual private networks.

Amazon RDS Overview & FAQs – Deep dive into managed database capabilities, licensing, and pricing structures.

Amazon RDS User Guide – Step-by-step documentation for deploying database clusters and managing replication.

TR

Modül 03: Uygulamalı Pratik – Temel Ağ Yönetimi ve Yönetilen Veri Tabanları
Bu modül, AWS ekosistemi içinde ağ izolasyon sınırlarının tanımlanması ve yönetilen veri tabanı katmanlarının ayağa kaldırılmasıyla ilgili pratik altyapı uygulamalarına odaklanmaktadır.

1. Temel Altyapı Bileşenlerini Anlamak
Amazon Virtual Private Cloud (VPC) Nedir?
Amazon VPC, AWS hesabı bütününde mantıksal olarak izole edilmiş, size özel tanımlı bir sanal ağ yapısıdır. Bulut üzerindeki kendi özel veri merkeziniz gibi çalışır ve ağ ortamınız üzerinde tam kontrol sahibi olmanızı sağlar.

Alt Ağlar (Subnets): Bir VPC'nin IP adresi aralığının bölümlere ayrılmış parçalarıdır.

Kamuya Açık Alt Ağlar (Public Subnets):* İnternet Ağ Geçidi (Internet Gateway) üzerinden dış dünyaya bağlıdır; web sunucuları gibi kullanıcıya açık kaynaklar için kullanılır.

Özel Alt Ağlar (Private Subnets):* Doğrudan internet erişimine kapalıdır; arka plan mantıkları (backend) ve veri depolama katmanları için kullanılır.

Güvenlik ve İzolasyon: Ağ trafiği, ağ seviyesinde Ağ Erişim Kontrol Listeleri (NACLs) ve kaynak seviyesinde Güvenlik Grupları (Security Groups - durum bilgisi koruyan güvenlik duvarları) ile sıkı bir şekilde denetlenir.

Amazon Relational Database Service (RDS) Nedir?
Amazon RDS, endüstri standardı ilişkisel veri tabanlarının (PostgreSQL, MySQL, MariaDB ve SQL Server gibi) bulutta kurulmasını, işletilmesini ve ölçeklenmesini kolaylaştıran, tam yönetimli (fully managed) bir veri tabanı servisidir.

Otomatik Yönetim: Donanım kurulumu, veri tabanı yazılım yamaları (patching), otomatik yedeklemeler ve hata tespiti gibi zaman alan yönetimsel görevler AWS tarafından üstlenilir.

Yüksek Erişilebilirlik (High Availability): Verileri farklı bir Erişilebilirlik Alanındaki (AZ) yedek bir örneğe otomatik ve eş zamanlı olarak kopyalayan Multi-AZ mimarisini destekler; böylece ana sunucuda bir arıza yaşandığında sistem kesintisiz devam eder.

2. Uygulamalı Mimari Senaryo: Güvenli Veri Tabanı İzolasyonu
Profesyonel düzeydeki bulut mühendisliğinde veri tabanları asla doğrudan kamuya açık internete maruz bırakılmaz. Standart mimari pratikleri, uygulama sunucularını kamuya açık (public) alt ağa yerleştirirken, veri tabanı katmanını özel (private) bir alt ağ içinde izole etmeyi gerektirir.

Pratik Uygulama İş Akışı (Workflow):
Ağ Yapılandırması: Özel bir VPC tanımlayın ve birden fazla Erişilebilirlik Alanına dağılacak şekilde genel ve özel alt ağ (subnet) blokları atayın.

Ağ Geçidi Ayarları: Genel alt ağların dış dünya ile trafik alışverişi yapabilmesi için bir İnternet Ağ Geçidi (IGW) bağlayın.

Veri Tabanı Dağıtımı: Bir Amazon RDS örneği başlatın ve bu örneği açıkça yeni oluşturduğunuz özel alt ağlara (private subnets) atayın.

Erişim Kontrolü (Güvenlik Duvarı): RDS için, gelen veri tabanı trafiğine (örneğin PostgreSQL için 5432 veya MySQL için 3306 portu) yalnızca uygulama sunucusunun güvenlik grubundan geliyorsa izin veren spesifik bir Güvenlik Grubu yapılandırın.

3. Referans Dokümantasyon ve Öğrenme Linkleri
Resmi AWS Kılavuzları:
Amazon VPC Genel Bakış ve SSS – Bulut ağları, alt ağlar ve uç nokta mimarilerinin detaylı incelemeleri.

Amazon VPC Kullanım Kılavuzu – Sanal özel ağların yapılandırılmasına ilişkin resmi teknik dokümantasyon.

Amazon RDS Genel Bakış ve SSS – Yönetilen veri tabanı yetenekleri, lisanslama ve fiyatlandırma yapılarına derinlemesine bakış.

Amazon RDS Kullanım Kılavuzu – Veri tabanı kümelerinin dağıtımı ve replikasyon yönetimi için adım adım teknik rehber.

