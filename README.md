# DevOps Temelleri

CI: 'Continuous Integration' demektir. Kodu her pushladığımızda otomatik test eder. Sorun çıkarsa gösterir.

CD: 'Continious Deployment' demektir. CI kısmını geçtiğinde CD çalışır ve uygulama otomatik güncellenir/yayınlanır.

Docker: Uygulamanı her yerde aynı şekilde çalıştırmanı sağlayan container teknolojisi.Databaseler, onlarca microservice'ler içinde barındırır.

Kubernetes: Kubernetes ise, Orkestra şefi görevini üstlenir. Docker container'ların nerde çalışacağına, kaçtane kopyasının olacağına, eğer biri bozulursa nasıl tepki verileceğine, nasıl güvenliği sağlayacaklarına karar veren sistemdir.


Infrastructure as Code (IaC)

----------

GIT & GITHUB:
    1 - git add & git commit komutlarıyla değiştirilen dosyalar eklenir.
    2 - git branch [branch_name] ile yeni dal oluşturulur.
    3 - git checkout [branch_name] ile verilen isimdeki branche gidilir.
    4 - Yeni branch oluşturup o dosyaya gitmenin kısa yolu 'git checkout -b [branch_name]'dir.
    5 - Eğer direkt olarak main'e bir branch açmamak, bir branch'in altına başka bir branch açmak istersek zincirleme olarak isimleri yazarız. Örneğin: git branch [newest-branch-name] [new-branch]
