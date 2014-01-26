---
layout: post
title: "GitHub Pages ve Jekyll ile blog olusturmak"
description: ""
category: 
tags: [gem install json, github, github pages, jekyll, jekyll serve, ruby, runner.rb:365]
---
{% include JB/setup %}

İlk olarak [Jekyll](http://jekyllrb.com/) nedir, ondan bahsedelim. `Jekyll`, statik içeriklerle site oluşturabildiğiniz bir araçtır. Ruby dili ile yazılmıştır. İçerik oluşturduğunuzda, header, sidebar, footer kısımları ( tabi kullandığınız temaya ve layout yapısına bağlı başka yerler de olabilir ) sabit kalır ve içerik kısmı url’e göre değişir.

[Github Pages](http://pages.github.com), projelerinize vs. websitesi oluşturabildiğiniz GitHub reponuzda host edilen, dolayısıyla terminalden git ile kontrol edebileceğiniz bir yapıdır.
Peki Jekyll’nin [GitHub](http://github.com) ile olayı nedir? Oluşturduğunuz bir GitHub Page içerisine, Jekyll push ettiğiniz takdirde, bir adet blogunuz olmakta. İşin özeti tamamen bu aslında.

Hızlıca bu işlemleri yapmak istiyorsanız, [şu linke](http://jekyllbootstrap.com/usage/jekyll-quick-start.html) tıklamanız yeterli. Adım adım ne yapacağınız yazıyor, ancak ben kısaca bahsedeyim.

İlk olarak github içerisinde `username.github.com` isminde bir repo oluşturuyorsunuz. Ardından bilgisayarınızda Jekyll’i clonelayıp, `remote set-url` ile oluşturduğunuz repoya gönderiyorsunuz. Ve `username.github.io` adresiniz yaklaşık bir 10 dakika içerisinde açılmış oluyor.

Linkini verdiğim sitede layoutları bootstrap ile yapılmış bir Jekyll var. Eğer isterseniz tabi ki kendiniz de temasını şeklini felan düzenleyebilirsiniz. Ayrıca eğer isterseniz mevcut bir Jekyll’den clonelayıp kendiniz bir tane oluşturabilirsiniz. Burada bir liste var örneğin : [https://github.com/jekyll/jekyll/wiki/Sites](https://github.com/jekyll/jekyll/wiki/Sites)

Postların tamamı, `./_posts` klasörünün altında bulunuyor. Eğer terminalden

	rake post title="deneme"

derseniz, `./_posts` klasörünün altında, current-date-deneme.md isminde bir dosya oluşuyor. Bu dosyayı herhangi bir editör ile düzenlediğinizde bir adet post yazmış oluyorsunuz. Ancak bu şekilde yapmak zorunda değilsiniz, `./_posts` altında herhangi bir dosya oluşturup onu `username.github.io/dosyaadi` şeklinde veya bir klasör oluşturup ardından onun altında dosya oluşturup `username.github.io/klasör/dosyaadi` şeklinde çalıştırabilirsiniz.

Jekyll’i localde çalıştırabilmek için bilgisayarınızda ayrıca `ruby` kurulu olması gerekiyor. Onu da [buradaki yazı](http://dubluve.net/2013/07/26/ubuntuya-ruby-kurulumu/)mda anlatmıştım, belki yardımcı olabilir.

Ayrıca localde çalışırken başıma gelen bir olay; `./_config.yml` dosyası `jekyll serve` dediğinizde load oluyor. Üzerinde değişiklik yaptığınızda tekrar jekyll serve demeniz gerekiyor. ( esasında tüm site  `./_site/` klasörünün altında oluşturuluyor. )

Localde çalışırken başıma gelen bir başka hata ise şu şekildeydi : 

	runner.rb:365:in require_program: program version required (Commander::Runner::CommandError)

Çözümü ise : 

	sudo gem install json

Jekyll’nin asıl amacı, yazılımcıların kod yazar gibi blog içeriği oluşturmalarıymış. Ufak bir araştırma yaptığımda kullanan sayısının bir hayli çok olduğunu da gördüm.
