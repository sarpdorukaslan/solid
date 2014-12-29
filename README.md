#SOLID Prensipleri

Solid prensipleri yazılım ile ilgili kullanılan 5 maddelik prensip serisidir. 
   Tasarım kalıplarına uygun programlar geliştirildiğinde bile bazı sorunlar çıkmış olup, 
SOLID bu sorunlara çözüm olarak tasarlanmıştır. 

####1) Esnemezlik (Rigitidy) : 
    Yazılımın geliştirilmesi ve ekleme yapılması ile ilgili sorunlar.
####2) Kırılganlık (Fragility) : 
    Yazılımın bir yerinde yapılan değişikliğin başka bir bölümü olumsuz etkilemesi.
####3) Sabitlik (Immobility) : 
    Geliştirilen bir bölümün başka bir yerde kullanılamaması. 

   Bu sorunlar sadece yazılımın sorunları değil, genel olarak yaşamımızda olan sorunlardır ve bunları 
otomatik olarak çözümleriz bazen. Bazende çözemediğimiz için sorunlarla karşılaşırız. 

   Bir örnek verelim: Bir lokanta açalım ve bunu yaparken SOLID'e nasıl uyduğumuza bakalım. 

##1) (S)ingle Responsibility (Tek Sorumluluk) : 
   Mutfağımızda tezgahımızı hem yemek malzemelerini doğramak hem servis hem bulaşık yıkamak için 
kullanıyor olsaydık ne olurdu? Hem müşteriler açısından "hijyenik" olmaktan uzak hemde orda çalışacak kişi ya da kişiler
için karmaşık bir durum olurdu. Bu durum aynı şekilde personel için de geçerli. Bir personeli hem bulaşıkçı hem garson 
hem komi olarak kullanırsak oluşacak sorunları tahmin etmek zor değil. 

   Bu, yazılımımız içindeki ayrıştırma için de önemli. En temelde fonksiyon/metodlarımız tek bir işi yapmalı,
sınıfımız tek bir işe yönelik olmalı, paketimiz/modülümüz/bileşenimiz tek bir işi yapmalı. 

##2) (O)pen/Closed (Geliştirmeye Açık/Değiştirmeye Kapalı) :
   Yine lokantamızın personelini seçerken sadece makarna yapan bir işletme olduğumuz varsayımı ile hareket edecek olursak, 
   makarna konusunda genişlemek için minimum değişikikle yapabilmek lazım. Malzeme değişiklikleri ile ürün yelpazesini 
   geniş tutmak mümkün olacaktır. 
   
   Personelimizi seçerken kendini geliştirebilen personelle çalışmak sık sık personel değişikliği yapmamızın önüne geçer. 

##3) (L)iskov’s Substitution:
   En basit hali ile üretilen yemeğimizin beklentinin çok uzağında olmaması lazım. 
   Örneğin müşteri tavkuklu makarna istediği zaman "makarnalı tavuk" gelmemeli önüne. 
   Ya da "şef garson" diye yetiştirilen yada işe alınan bir personelin aşçıbaşı olması durumu nasıl kabul edilemez bir durum ise
   türeyen sınıflarında benzer şekilde planlanması gerekmektedir.
   
##4) (I)Nterface Segregation: 
   Bütün personelin ve yemeklerin ana tanımlarının yapılmış olması gerekmektedir. Personel için "görev tanımı", 
   yemek için "tarif" buna örneklenebilir. Ve bu tanım ve tarifleri kullanırken öyle ayrıştırmalıyız ki değişik yapılar için
   sorunlar çıkmasın. Örneğin, kremalı mantarlı tavuklu makarna hazırlanırken krema mantar ve tavuk birlikte soslu halde 
   hazır durursa müşteri, "Ben kremalı mantarlı istiyorum." dediğinde sosun içinden tavuk ayıklamak zorunda kalmamak lazım. 
   
   Sınıfımızı tanımlarken hem kurallara uydurmalı hemde esnek olmasını sağlamamız gerekmektedir. 
   
##5) (D)Ependency Inversion:
  Makarnalarımızı "Filiz makarnadan" alıyoruz ibaresinin bulunması ya da personelinizin ismi ile çağrılmasını istemeniz 
  bunlara örnektir. Filiz makarna yerine başka makarna kullanmak istediğinizde veya Ertuğrul Şef işten ayrıldığında 
  bir bocalama yaşamama şansınız yok. 
  
  Aynı şekilde sınıflarımız başka sınıflara, paketlerimiz/modüllerimiz/bileşenlerimiz dışardaki başka yerlere bağımlı olmamalı. 
  
  Yukarda kabaca anlatmaya çalıştığım yapılanma ile daha esnek daha az kırılgan ve çalışma iş modelini istediğimiz yere 
  uyarlayabilir durumda oluruz. Örnekler çoğaltılabilir. Yazılım açısından bu prensiplerin uygulanmış olması ya da tek başına bu 
  kurallara uyulmuş olması önemsizdir. Yazılan kod bir şekilde çalışır. Ancak yazılımın gelişmesi büyümesi ve ölçeklenebilmesi 
  açısından Tasarım Desenleri ile birlikte kullanılması ilerleyen projeler için büyük avantaj sağlayacaklardır. 
  
  SOLID prensipleri tek başına mucizeler yaratan bir sorun çözücü değildir. Yazılım geliştiricilerin karşılaştığı sorunları 
  en aza indirmek için oluşturulmuş şablonlardan bir tanesidir. 
  
  Biz yukardaki sayılanları günlük yaşamımızda bir şekilde gerçekleştiriyoruz farkında olmadan. Şimdi yazılım açısından bu 
  kuralları örnekleyelim. 
  
##1) (S)ingle Responsibility: 

##### Yanlış Örnek: 
```php
Class Araba {
   function motor()
   {
     if ($benzinVarmi() != false)
     {
       $motorDurumu = calistir();
     }
   
   }
   
   function benzinVarmi()
   {
     return depoDaNeKadarYakitVar();
   }
   
   function depodaNeKadarYakitVar()
   {
     $depo = $this->depo;
     $yakitDurumu = $depo->yakitDurumu;
     if ($yakitDurumu > 0)
       return $yakitDurumu
     
     return false;
   }
   
   function depoDurumu()
   {
     $yakitYuksekligi = 10;
     $herCmDeKacLitreYakitVar = 4;
     $this->depo = $yakitYuksekligi * $herCmDeKacLitreYakitVar;
   }
}
```

Yukardaki kodumuzda neredeyse bütün kuralları yıkmaya yönelik davrandık :)) 

   Bu örneği daha da uzatabiliriz; bir arabada olması gereken her şeyi burada fonksiyon olarak yazın. 
Peki bunun nesi yanlış? Araba sınıfı ve sadece araba ile ilgili fonksiyonlar var. Tek sorumluluk değil mi? 

   İşte burda yazılımcının karar mekanizması devreye giriyor. Şu an bizim yaptğımız şey dökme araba yapmak. 
Bunu modifiye etmek bazı özelliklerini değiştirmek neredeyse yeni araba yapmaktan daha zor olacak. :) 
Bunu basitleştirmek için uygun bölümlere ayırmamız gerekiyor. Ve her bölüm için, bölümün yapacağı işi yapmasını sağlıyoruz. 
Başka bir şekilde örnekleyelim. Almanya'da çalışanların genel bir betimlemesi vardır "Adam fabrikada adam çalıştırıyor 
sadece vida sıkmak için." Sorumluluk alanı belli ve net sınıflar, metodlar, fonksiyonlar, paketler üretmek yazılımınızı 
daha güçlü kılacaktır. 

##### Doğru Örnek: 
```php
Class  Araba {
    function motor()
    {
        $motor = new Motor();
        try {
          $motor->calistir();
        }catch(BenzinException $e)
        {
          Uyari::goster($e->message());
        }
        catch(ArizaException $e)
        {
         Alarm::cal($e->message);
        }
    }
}
```


##2) (O)pen/Closed

##### Yanlış Örnek: 

```php
Class Notlar {
  public $not1;
  public $not2;
  public $not3;
  protected $sonuc
  
  function hesapla()
  {
        $this->sonuc = ($this->not1 +  $this->not2 + $this->not3)/3;
  }
  
}
```

Buradaki örnekte fonksiyonumuz sadece hesaplıyor evet. Sorun nerede? Bir not daha eklemek istediğimizde ne olacak? 
Hatta 2 not ortalamasını nasıl alacağız? Bu kodu geliştirmek için değişiklik yapmak zorundayız. Tabi bu, örnekleme için 
çok kaba bir örnek yazılımda istenen şey, bir değişiklik geliştirme yapılacağız zaman önceden yazılmış koda minimum 
müdahale gerekmesi üzerine. 

##### Doğru Örnek: 

```php
Class Notlar {
  public $notlar;

  protected $sonuc
  
  function hesapla()
  {
        $toplamNot = 0;
        foreach($this->notlar as $not)
        {
            $toplamNot += $not;
        }
        $this->sonuc = $toplamNot/count($this->notlar);
  }
  
}
```

##3) (L)iskov’s Substitution:

SOLID prensiplerinden anlaması en zor olanı (bana göre). Çok kaba bir örnek vermek gerekirse; 
siyahi bir çocuk gördüğünüzde anne yada babasının en azından birinin siyahi olmasını beklersiniz.

##### Yanlış Örnek: 

```php
Class Dikdortgen {
  private $yukseklik;
  private $genislik;

  protected $alan;
  
  function __set($kenar,$deger)
  {
    $this->$alan = $deger;
  }
  
  
  function alan()
  {
   return $this->yukseklik * $this->genislik;
  }
  
}

Class Kare Extends Dikdortgen {
  private $yukseklik;
  private $genislik;

  protected $alan;
  
  function __set($kenar,$deger)
  {
    $this->yukseklik = $this->genislik = $deger;
  }
  
  
  function alan()
  {
   return $this->yukseklik * $this->genislik;
  }
  
}

$kare = new Kare();

$kare->genislik = 5;
$kare->yukseklik = 10; 

echo $kare->alan();
```

Yukardaki örnekte basit bir ifade olan "Dikdörtgenin kenarları eşitse karedir. Ya da her kare bir dikdörtgendir." ifadesini 
kodlamış durumdayız.

Şimdi beklenen sonuç = 50 karşılaşılan sonuç = 100

##4) (I)nterface Segregation
Arayüzlerin ayrıştırılması. 

Aslında kurduğumuz cümlelerde bu ayrıştırmayı çok seri yapıyoruz fakat kod yazarken bunu gözden çok kaçırıyoruz. 
Örnek : 
"ya 1.6 dizel Renault sedan otomobil aldım" dediğinizde bunu otomatik yapıyor oluyoruz. 

##### Yanlış Örnek: 
```php
Class AldigimAraba implements Cc16DizelSedanInterface
{
  
}
```
##### Doğru Örnek: 
```php
Class AldigimAraba implements Cc16InterFace, DizelInterFace, SedanInterFace
{
  
}
```

##5) (D)ependency Inversion Prensibi

Dışa bağımlılıklarda tek bir yere bağımlı olmama durumunun sağlanması. 

##### Yanlış Örnek: 
```php
Class BenzinliMotor()
{
  
  function benzinal()
  {
    $benzinlik = new ShellBenzinlik();
    $benzinlik->pompaci()->doldur(50);
  }

}
```
   Aldığımız arabada "Benzini Shell'den alacaksın." gibi bir zorunluluk olsa idi ne kadar kızardık değil mi? 
Fakat kendi sınıflarımıza paketlerimize bileşenlerimize bunu yapmaktan hiç çekinmiyoruz. Neden acaba?

##### Doğru Örnek: 

```php
Class BenzinliMotor()
{
  
  function benzinal(Benzinlik $benzinlik)
  {
    $benzinlik->pompaci()->doldur(50);
  }

}
```

Bonus : 

### Inversion Of Control

Şimdi yukarda örneğimizde Benzinlik olan herhangi bir yere girip benzin alacağımızı belirttik.
Peki "hangi benzinlik" olacağına nerde karar vereceğiz? Verdiğimiz kararı nasıl iileteceğiz?

işte bu yapı için kullanılan yapılardan bir tanesi IoC Container yapısı. 
IoC bir zorunluluk değil "desen,kalıp" ne diye adlandırırsanız adlandırın "çözüm"dür.

Popüler PHP çatılarından laravel'de IoC çözümlemesi üzerine özellikle durulmuştur. 
##Örnek
```php
App::bind('Benzinlik', function($app)
{
    return new ShellBenzinlik;
});
``` 

##Örnek
```php
        $app->bind('Authority\Repo\Session\SessionInterface', function($app)
        {
            return new SentrySession(
            	$app['sentry']
            );
        });

//aşağıdakiinterfaceden üretilmiş bir sınıf tanımlaman lazım :))) namespace kullanmış
namespace Authority\Repo\Session;
interface SessionInterface
{

}
```
```php

        $app->bind('Authority\Service\Form\Login\LoginForm', function($app) // Loginform $login tanımlarsan
        {
            return new LoginForm(  //LoginForm classında bir nesne yaratırsın
                new LoginFormLaravelValidator( $app['validator'] ), //Loginform() iinde tanımladngına göre constructor, demek ki aynı anda LoginFormlaravelValidator yaratılacak 
                $app->make('Authority\Repo\Session\SessionInterface') // ve SessionInterface yaratılacak ? :/ yani LoginForm($param1, $param2) şeklinde o yüzden içini doldurmuş?
            );
        });
        
        
$app->bind('benzinlik',$app)
{
    return new ShellBenzinlik();
} 


//LoginForm.php nin constructor u
	public function __construct(ValidableInterface $validator, SessionInterface $session) //demek ki doğru anlamısım
	{
		$this->validator = $validator;
		$this->session = $session;
	}




//Burda tanımladığın şeyi kullanmak için

$benzinlik = $app->make('benzinlik'); 
```
#Teşekkürler
SOLID prensiplerini anlamamda ve bu dökümanı hazırlamamda kaynak olan yazı : 
http://www.clubcrema.com/index.php/2013/05/solid-prensipleri-solid-principles/		
