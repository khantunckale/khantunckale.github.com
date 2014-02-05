---
layout: post
title: "E: dpkg was interrupted | dpkg   configure  a' problemi (ubuntu)"
description: ""
category:
tags: [ubuntu, dpkg, linux]
---
{% include JB/setup %}
Ubuntu'ya gelen güncellemeyi update-manager ile kurmaya çalışıyordum. Ancak uzun süre geçmesine rağmen update-manager durdu ve kapatılamaz hale geldi. Komut satırından da kill edemedim çalışan processi.

Bilgisayarı yeniden başlattım, ardından komut satırından apt-get update yapmak istedim. Aldığım hata;

```
"E: dpkg was interrupted, you must manually run 'sudo dpkg --configure -a' to correct the problem."
```

Sebebi kurmak istediğim paketlerin dpkg ayarları ile ilgiliymiş. Bu aşamada tekrar update-manager açıp güncellemeyi oradan yapmaya çalışırsanız, üstte anlattığım durum tekrar karşınıza çıkacak ve bilgisayarı yeniden başlatmak zorunda kalacaksınız.

Durumu çözebilmek için ilk önce şu komutu çalıştırıp, kurulması yarım kalan paketleri fixliyoruz.

```
sudo apt-get install -f
```

Ardından şu komutu çalıştırarak dpkg konfigurasyonunu düzenleyip, iptal ettiğimiz paketleri kuruyoruz.

```
sudo dpkg --configure -a
```


