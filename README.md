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


----------

CI / CD: Kodun otomatik review edilmesi ve yayınlanmasını sağlayan 'github action' özelliğidir(alternatifleri gitlab,azure vs). 'YAML' uzantısı kullanılır ve oldukça sade yazılır. Açılımı oldukça komik : "YAML Ain't Markup Language". Python gibi white space üzerine yazılır, bir boşluğun bile anlamı vardır.

Bunların yanında YAML kendi içerisinde keywords'leri ve syntax'ları vardır. Bunlar:

    - name: Workflow'u veya işin başlık bilgisini barındırır(title)

    - on: Trigger'ları tanımlar (push,PR,schedule). Hangi işlem olduğunda CI başlasın?

    - jobs: Yapılacak işleri, OS(operation system) ve adımları tanımlar.

    - steps: Sıralı komutlar veya aksiyonlar

    - run: Uygulamayı execute etmek için shell commands'leri.

    - uses: Önceden oluşturulmuş eylemler(prebuilt actions)

    - with: Yapılacak aksiyonlar için paratmereler 

    - env: Environment variables

    - need: Bir işi(job) diğerine bağlar

Bir tane workflow oluşturalım:

name: CI Pipeline 

on:
  push:
    branches:
      - main 


jobs:
  build:
    runs-on:ubuntu-latest

  steps:
    - name: Checkout Code
      uses: actions/checkout@v5

    - name: Install dependencies
      run: npm install

    - name: Run tests
      run: npm test


NOT: Hazır actionlar, github üzerinden bulunabilinir. Hazır template'lerde bulunur !