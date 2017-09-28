KAYNAK : Tayfun ERBİLEN 
<br>
Yazı : https://www.erbilen.net/ubuntu-icin-xampp-kurulumu/
<br>
Web Site : https://www.erbilen.net
<br>
YouTube : https://www.youtube.com/user/uzmanvideo
<br>
Facebook : https://facebook.com/erbilennet
<br>
Twitter : https://twitter.com/tayfunerbilen

<P>Yeni XAMPP Sürümüne göre Güncellenmiştir.

<h1>Ubuntu için Xampp Kurulumu</h1>

<p>Ubuntu için xampp kurulumu hakkında bir derleme yaptım sizin için.</p>

<p>1) İlk olarak xampp’ın web sitesinden linux için olan download linkini bir alalım. Ben 64bit kuracağım için aşağıdaki link benim için kafi;
  
<p>
https://sourceforge.net/projects/xampp/files/XAMPP%20Linux/7.1.9/xampp-linux-x64-7.1.9-0-installer.run
</p>

<p>2) Şimdi CTRL + ALT + T kısayolu ile terminalimizi açalım.</p>

![](https://www.erbilen.net/wp-content/uploads/2014/03/terminal-goruntusu.png)

<p>3) Yukarıdaki download linkini wget komutundan sonra yapıştıralım. Ve xampp’ı indirmeye başlayalım.</p>

```sh 
wget https://sourceforge.net/projects/xampp/files/XAMPP%20Linux/7.1.9/xampp-linux-x64-7.1.9-0-installer.run 
```


![](https://i0.wp.com/www.erbilen.net/wp-content/uploads/2014/03/xampp-download.png)


<p>4) Şimdi mevcut dosyaları görmek için terminal’e ls yazıp çalıştırın.</p>

<p>Gördüğünüz gibi indirdiğimiz dosya orada gözüküyor  Artık kuruluma geçebiliiriz.</p>

![](https://i1.wp.com/www.erbilen.net/wp-content/uploads/2014/03/ss1.png)

<p>5) Dosyamızın chmod’unu ayarlayalım.</p>

```sh
sudo chmod +x xampp-linux-x64-7.1.9-0-installer.run
```
  
Çalıştırdığınızda eğer parola istiyorsa mevcut parolanızı yazıp enter’a basın. İlk defa kullanıyorsanız parola yazmıyor gibi gözükebilir ama yazdığınız parola işliyor sıkıntı yok yani</p>

<p>6) Artık xampp kurulumunu başlatabiliriz.</p>

```sh 
sudo ./xampp-linux-x64-7.1.9-0-installer.run
  ```

![](https://www.erbilen.net/wp-content/uploads/2014/03/ss2.png)

<p>Bunda sonrası bildiğimiz kurulum.. Next next next diyerek devam edebilirsiniz.</p>

<p>7) Xampp için izinleri ayarlamamız gerekiyor. Yoksa yeni dosya oluşturamayız ya da dosyalar üzerinde değişiklik yapamayız.. İlk olarak terminal’e clear diyerek temizleyelim.. Ve who am i komutunu çalıştırarak kullanıcı adımızı orada bir görelim.</p>


``` sh
who-am-i
```



![](https://www.erbilen.net/wp-content/uploads/2014/03/who-am-i.png)


<p>Örneğin benim kullanıcı adım ubuntu imiş  Buna göre şu kodu çalıştırmam gerekiyor.</p>

``` sh 
sudo chown -R ubuntu:ubuntu /opt/lampp/htdocs
```
Son olarak httpd.conf dosyasında bir değişiklik yapmamız gerekiyor. Şu komut satırını çalıştıralım.</p>

``` sh 
sudo gedit /opt/lampp/etc/httpd.conf
```
Bir dosya açılmış olması gerekiyor. Bu dosya içinde CTRL + F ile User şeklinde aratın. Sonunda boşluk olacak şekilde.</p>


![](https://www.erbilen.net/wp-content/uploads/2014/03/ss3.png)


<p>User’dan sonra gelen daemon kısmını kendi kullanıcı adınızla değiştirin.</p>

<h1>Servisleri başlatmak ve durdurmak</h1>

<p>Bunun için bir bash script yazdım wget ile indirerek xampp servislerini başlatmak ve kapatmak daha kolay;</p>

```sh 
wget https://raw.githubusercontent.com/secilmiskisi/XAMPPBaslatici/master/xampp.sh
```
Kullanımı hakkında https://github.com/secilmiskisi/XAMPPBaslatici

</p>

