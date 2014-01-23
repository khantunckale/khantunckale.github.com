---
layout: post
title: "ubuntu'ya ruby kurulumu"
description: ""
category: 
tags: [ruby, rvm, ubuntu]
---
{% include JB/setup %}

## ubuntu'ya ruby kurulumu

Ruby kurulumunda 2 seçenek var. Biri RVM olmadan, biri RVM ile. ( RVM = Ruby Version Manager )

### RVM olmadan kurulum
İlk olarak terminali açıyoruz. Ardından ruby 1.9.3 versiyonunu kuruyoruz.

	sudo apt-get update
	sudo apt-get install ruby1.9.3

Kurduktan sonra

	ruby --version

diyerek kurulduğunu görmüş oluruz.

### RVM ile kurulum

Eğer sisteminizde curl kurulu değilse ilk olarak curl kurunuz.

	sudo apt-get install curl

Ardından şu işlemleri yapınız.

	curl -L get.rvm.io | bash -s stable
	source /usr/local/rvm/scripts/rvm

RVM için gerekli paketlerin kurulu olup olmadığına bakıyoruz, eğer gerekli paketler varsa kuruyoruz. Şu şekilde ;

	rvm requirements

Son bir işlemimiz kalıyor;

	rvm install 1.9.3