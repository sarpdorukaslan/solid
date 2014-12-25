#SOLID Prensipleri

Solid prensipleri yazÄ±lÄ±m ile ilgili kullanÄ±lan 5 maddelik prensip serisidir. 
   TasarÄ±m kalÄ±plarÄ±na uygun programlar geliÅŸtirildiÄŸinde bile bazÄ± sorunlar Ã§Ä±kmÄ±ÅŸ olup, 
SOLID bu sorunlara Ã§Ã¶zÃ¼m olarak tasarlanmÄ±ÅŸtÄ±r. 

####1) Esnemezlik (Rigitidy) : 
    YazÄ±lÄ±mÄ±n geliÅŸtirilmesi ve ekleme yapÄ±lmasÄ± ile ilgili sorunlar.
####2) KÄ±rÄ±lganlÄ±k (Fragility) : 
    YazÄ±lÄ±mÄ±n bir yerinde yapÄ±lan deÄŸiÅŸikliÄŸin baÅŸka bir bÃ¶lÃ¼mÃ¼ olumsuz etkilemesi.
####3) Sabitlik (Immobility) : 
    GeliÅŸtirilen bir bÃ¶lÃ¼mÃ¼n baÅŸka bir yerde kullanÄ±lamamasÄ±. 

   Bu sorunlar sadece yazÄ±lÄ±mÄ±n sorunlarÄ± deÄŸil, genel olarak yaÅŸamÄ±mÄ±zda olan sorunlardÄ±r ve bunlarÄ± 
otomatik olarak Ã§Ã¶zÃ¼mleriz bazen. Bazende Ã§Ã¶zemediÄŸimiz iÃ§in sorunlarla karÅŸÄ±laÅŸÄ±rÄ±z. 

   Bir Ã¶rnek verelim: Bir lokanta aÃ§alÄ±m ve bunu yaparken SOLID'e nasÄ±l uyduÄŸumuza bakalÄ±m. 

##1) (S)ingle Responsibility (Tek Sorumluluk) : 
   MutfaÄŸÄ±mÄ±zda tezgahÄ±mÄ±zÄ± hem yemek malzemelerini doÄŸramak hem servis hem bulaÅŸÄ±k yÄ±kamak iÃ§in 
kullanÄ±yor olsaydÄ±k ne olurdu? Hem mÃ¼ÅŸteriler aÃ§Ä±sÄ±ndan "hijyenik" olmaktan uzak hemde orda Ã§alÄ±ÅŸacak kiÅŸi ya da kiÅŸiler
iÃ§in karmaÅŸÄ±k bir durum olurdu. Bu durum aynÄ± ÅŸekilde personel iÃ§in de geÃ§erli. Bir personeli hem bulaÅŸÄ±kÃ§Ä± hem garson 
hem komi olarak kullanÄ±rsak oluÅŸacak sorunlarÄ± tahmin etmek zor deÄŸil. 

   Bu, yazÄ±lÄ±mÄ±mÄ±z iÃ§indeki ayrÄ±ÅŸtÄ±rma iÃ§in de Ã¶nemli. En temelde fonksiyon/metodlarÄ±mÄ±z tek bir iÅŸi yapmalÄ±,
sÄ±nÄ±fÄ±mÄ±z tek bir iÅŸe yÃ¶nelik olmalÄ±, paketimiz/modÃ¼lÃ¼mÃ¼z/bileÅŸenimiz tek bir iÅŸi yapmalÄ±. 

##2) (O)pen/Closed (GeliÅŸtirmeye AÃ§Ä±k/DeÄŸiÅŸtirmeye KapalÄ±) :
   Yine lokantamÄ±zÄ±n personelini seÃ§erken sadece makarna yapan bir iÅŸletme olduÄŸumuz varsayÄ±mÄ± ile hareket edecek olursak, 
   makarna konusunda geniÅŸlemek iÃ§in minimum deÄŸiÅŸikikle yapabilmek lazÄ±m. Malzeme deÄŸiÅŸiklikleri ile Ã¼rÃ¼n yelpazesini 
   geniÅŸ tutmak mÃ¼mkÃ¼n olacaktÄ±r. 
   
   Personelimizi seÃ§erken kendini geliÅŸtirebilen personelle Ã§alÄ±ÅŸmak sÄ±k sÄ±k personel deÄŸiÅŸikliÄŸi yapmamÄ±zÄ±n Ã¶nÃ¼ne geÃ§er. 

##3) (L)iskovâ€™s Substitution:
   En basit hali ile Ã¼retilen yemeÄŸimizin beklentinin Ã§ok uzaÄŸÄ±nda olmamasÄ± lazÄ±m. 
   Ã–rneÄŸin mÃ¼ÅŸteri tavkuklu makarna istediÄŸi zaman "makarnalÄ± tavuk" gelmemeli Ã¶nÃ¼ne. 
   Ya da "ÅŸef garson" diye yetiÅŸtirilen yada iÅŸe alÄ±nan bir personelin aÅŸÃ§Ä±baÅŸÄ± olmasÄ± durumu nasÄ±l kabul edilemez bir durum ise
   tÃ¼reyen sÄ±nÄ±flarÄ±nda benzer ÅŸekilde planlanmasÄ± gerekmektedir.
   
##4) (I)Nterface Segregation: 
   BÃ¼tÃ¼n personelin ve yemeklerin ana tanÄ±mlarÄ±nÄ±n yapÄ±lmÄ±ÅŸ olmasÄ± gerekmektedir. Personel iÃ§in "gÃ¶rev tanÄ±mÄ±", 
   yemek iÃ§in "tarif" buna Ã¶rneklenebilir. Ve bu tanÄ±m ve tarifleri kullanÄ±rken Ã¶yle ayrÄ±ÅŸtÄ±rmalÄ±yÄ±z ki deÄŸiÅŸik yapÄ±lar iÃ§in
   sorunlar Ã§Ä±kmasÄ±n. Ã–rneÄŸin, kremalÄ± mantarlÄ± tavuklu makarna hazÄ±rlanÄ±rken krema mantar ve tavuk birlikte soslu halde 
   hazÄ±r durursa mÃ¼ÅŸteri, "Ben kremalÄ± mantarlÄ± istiyorum." dediÄŸinde sosun iÃ§inden tavuk ayÄ±klamak zorunda kalmamak lazÄ±m. 
   
   SÄ±nÄ±fÄ±mÄ±zÄ± tanÄ±mlarken hem kurallara uydurmalÄ± hemde esnek olmasÄ±nÄ± saÄŸlamamÄ±z gerekmektedir. 
   
##5) (D)Ependency Inversion:
  MakarnalarÄ±mÄ±zÄ± "Filiz makarnadan" alÄ±yoruz ibaresinin bulunmasÄ± ya da personelinizin ismi ile Ã§aÄŸrÄ±lmasÄ±nÄ± istemeniz 
  bunlara Ã¶rnektir. Filiz makarna yerine baÅŸka makarna kullanmak istediÄŸinizde veya ErtuÄŸrul Åef iÅŸten ayrÄ±ldÄ±ÄŸÄ±nda 
  bir bocalama yaÅŸamama ÅŸansÄ±nÄ±z yok. 
  
  AynÄ± ÅŸekilde sÄ±nÄ±flarÄ±mÄ±z baÅŸka sÄ±nÄ±flara, paketlerimiz/modÃ¼llerimiz/bileÅŸenlerimiz dÄ±ÅŸardaki baÅŸka yerlere baÄŸÄ±mlÄ± olmamalÄ±. 
  
  Yukarda kabaca anlatmaya Ã§alÄ±ÅŸtÄ±ÄŸÄ±m yapÄ±lanma ile daha esnek daha az kÄ±rÄ±lgan ve Ã§alÄ±ÅŸma iÅŸ modelini istediÄŸimiz yere 
  uyarlayabilir durumda oluruz. Ã–rnekler Ã§oÄŸaltÄ±labilir. YazÄ±lÄ±m aÃ§Ä±sÄ±ndan bu prensiplerin uygulanmÄ±ÅŸ olmasÄ± ya da tek baÅŸÄ±na bu 
  kurallara uyulmuÅŸ olmasÄ± Ã¶nemsizdir. YazÄ±lan kod bir ÅŸekilde Ã§alÄ±ÅŸÄ±r. Ancak yazÄ±lÄ±mÄ±n geliÅŸmesi bÃ¼yÃ¼mesi ve Ã¶lÃ§eklenebilmesi 
  aÃ§Ä±sÄ±ndan TasarÄ±m Desenleri ile birlikte kullanÄ±lmasÄ± ilerleyen projeler iÃ§in bÃ¼yÃ¼k avantaj saÄŸlayacaklardÄ±r. 
  
  SOLID prensipleri tek baÅŸÄ±na mucizeler yaratan bir sorun Ã§Ã¶zÃ¼cÃ¼ deÄŸildir. YazÄ±lÄ±m geliÅŸtiricilerin karÅŸÄ±laÅŸtÄ±ÄŸÄ± sorunlarÄ± 
  en aza indirmek iÃ§in oluÅŸturulmuÅŸ ÅŸablonlardan bir tanesidir. 
  
  Biz yukardaki sayÄ±lanlarÄ± gÃ¼nlÃ¼k yaÅŸamÄ±mÄ±zda bir ÅŸekilde gerÃ§ekleÅŸtiriyoruz farkÄ±nda olmadan. Åimdi yazÄ±lÄ±m aÃ§Ä±sÄ±ndan bu 
  kurallarÄ± Ã¶rnekleyelim. 
  
##1) (S)ingle Responsibility: 

##### YanlÄ±ÅŸ Ã–rnek: 
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

Yukardaki kodumuzda neredeyse bÃ¼tÃ¼n kurallarÄ± yÄ±kmaya yÃ¶nelik davrandÄ±k :)) 

   Bu Ã¶rneÄŸi daha da uzatabiliriz; bir arabada olmasÄ± gereken her ÅŸeyi burada fonksiyon olarak yazÄ±n. 
Peki bunun nesi yanlÄ±ÅŸ? Araba sÄ±nÄ±fÄ± ve sadece araba ile ilgili fonksiyonlar var. Tek sorumluluk deÄŸil mi? 

   Ä°ÅŸte burda yazÄ±lÄ±mcÄ±nÄ±n karar mekanizmasÄ± devreye giriyor. Åu an bizim yaptÄŸÄ±mÄ±z ÅŸey dÃ¶kme araba yapmak. 
Bunu modifiye etmek bazÄ± Ã¶zelliklerini deÄŸiÅŸtirmek neredeyse yeni araba yapmaktan daha zor olacak. :) 
Bunu basitleÅŸtirmek iÃ§in uygun bÃ¶lÃ¼mlere ayÄ±rmamÄ±z gerekiyor. Ve her bÃ¶lÃ¼m iÃ§in, bÃ¶lÃ¼mÃ¼n yapacaÄŸÄ± iÅŸi yapmasÄ±nÄ± saÄŸlÄ±yoruz. 
BaÅŸka bir ÅŸekilde Ã¶rnekleyelim. Almanya'da Ã§alÄ±ÅŸanlarÄ±n genel bir betimlemesi vardÄ±r "Adam fabrikada adam Ã§alÄ±ÅŸtÄ±rÄ±yor 
sadece vida sÄ±kmak iÃ§in." Sorumluluk alanÄ± belli ve net sÄ±nÄ±flar, metodlar, fonksiyonlar, paketler Ã¼retmek yazÄ±lÄ±mÄ±nÄ±zÄ± 
daha gÃ¼Ã§lÃ¼ kÄ±lacaktÄ±r. 

##### DoÄŸru Ã–rnek: 
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

##### YanlÄ±ÅŸ Ã–rnek: 

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

Buradaki Ã¶rnekte fonksiyonumuz sadece hesaplÄ±yor evet. Sorun nerede? Bir not daha eklemek istediÄŸimizde ne olacak? 
Hatta 2 not ortalamasÄ±nÄ± nasÄ±l alacaÄŸÄ±z? Bu kodu geliÅŸtirmek iÃ§in deÄŸiÅŸiklik yapmak zorundayÄ±z. Tabi bu, Ã¶rnekleme iÃ§in 
Ã§ok kaba bir Ã¶rnek yazÄ±lÄ±mda istenen ÅŸey, bir deÄŸiÅŸiklik geliÅŸtirme yapÄ±lacaÄŸÄ±z zaman Ã¶nceden yazÄ±lmÄ±ÅŸ koda minimum 
mÃ¼dahale gerekmesi Ã¼zerine. 

##### DoÄŸru Ã–rnek: 

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

##3) (L)iskovâ€™s Substitution:

SOLID prensiplerinden anlamasÄ± en zor olanÄ± (bana gÃ¶re). Ã‡ok kaba bir Ã¶rnek vermek gerekirse; 
siyahi bir Ã§ocuk gÃ¶rdÃ¼ÄŸÃ¼nÃ¼zde anne yada babasÄ±nÄ±n en azÄ±ndan birinin siyahi olmasÄ±nÄ± beklersiniz.

##### YanlÄ±ÅŸ Ã–rnek: 

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

$dikdortgen = new Kare();

$kare->genislik = 5;
$kare->yukseklik = 10; 

echo $kare->alan();
```

Yukardaki Ã¶rnekte basit bir ifade olan "DikdÃ¶rtgenin kenarlarÄ± eÅŸitse karedir. Ya da her kare bir dikdÃ¶rtgendir." ifadesini 
kodlamÄ±ÅŸ durumdayÄ±z.

Åimdi beklenen sonuÃ§ = 50 karÅŸÄ±laÅŸÄ±lan sonuÃ§ = 100

##4) (I)nterface Segregation
ArayÃ¼zlerin ayrÄ±ÅŸtÄ±rÄ±lmasÄ±. 

AslÄ±nda kurduÄŸumuz cÃ¼mlelerde bu ayrÄ±ÅŸtÄ±rmayÄ± Ã§ok seri yapÄ±yoruz fakat kod yazarken bunu gÃ¶zden Ã§ok kaÃ§Ä±rÄ±yoruz. 
Ã–rnek : 
"ya 1.6 dizel renoult sedan otomobil aldÄ±m" dediÄŸinizde bunu otomatik yapÄ±yor oluyoruz. 

##### YanlÄ±ÅŸ Ã–rnek: 
```php
Class AldigimAraba implements Cc16DizelSedanInterface
{
  
}
```
##### DoÄŸru Ã–rnek: 
```php
Class AldigimAraba implements Cc16InterFace, DizelInterFace, SedanInterFace
{
  
}
```

##5) (D)ependency Inversion Prensibi

DÄ±ÅŸa baÄŸÄ±mlÄ±lÄ±klarda tek bir yere baÄŸÄ±mlÄ± olmama durumunun saÄŸlanmasÄ±. 

##### YanlÄ±ÅŸ Ã–rnek: 
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
   AldÄ±ÄŸÄ±mÄ±z arabada "Benzini Shell'den alacaksÄ±n." gibi bir zorunluluk olsa idi ne kadar kÄ±zardÄ±k deÄŸil mi? 
Fakat kendi sÄ±nÄ±flarÄ±mÄ±za paketlerimize bileÅŸenlerimize bunu yapmaktan hiÃ§ Ã§ekinmiyoruz. Neden acaba?

##### DoÄŸru Ã–rnek: 

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

Åimdi yukarda Ã¶rneÄŸimizde Benzinlik olan herhangi bir yere girip benzin alacaÄŸÄ±mÄ±zÄ± belirttik.
Peki "hangi benzinlik" olacaÄŸÄ±na nerde karar vereceÄŸiz? VerdiÄŸimiz kararÄ± nasÄ±l iileteceÄŸiz?

iÅŸte bu yapÄ± iÃ§in kullanÄ±lan yapÄ±lardan bir tanesi IoC Container yapÄ±sÄ±. 
IoC bir zorunluluk deÄŸil "desen,kalÄ±p" ne diye adlandÄ±rÄ±rsanÄ±z adlandÄ±rÄ±n "Ã§Ã¶zÃ¼m"dÃ¼r.

PopÃ¼ler PHP Ã§atÄ±larÄ±ndan laravel'de IoC Ã§Ã¶zÃ¼mlemesi Ã¼zerine Ã¶zellikle durulmuÅŸtur. 
##Ã–rnek
```php
App::bind('Benzinlik', function($app)
{
    return new ShellBenzinlik;
});
``` 

##Ã–rnek
```php
        $app->bind('Authority\Repo\Session\SessionInterface', function($app)
        {
            return new SentrySession(
            	$app['sentry']
            );
        });

//aÅŸaÄŸÄ±dakiinterfaceden Ã¼retilmiÅŸ bir sÄ±nÄ±f tanÄ±mlaman lazÄ±m :))) namespace kullanmÄ±ÅŸ
namespace Authority\Repo\Session;
interface SessionInterface
{

}
```
```php

        $app->bind('Authority\Service\Form\Login\LoginForm', function($app) // Loginform $login tanÄ±mlarsan
        {
            return new LoginForm(  //LoginForm classÄ±nda bir nesne yaratÄ±rsÄ±n
                new LoginFormLaravelValidator( $app['validator'] ), //Loginform() iinde tanÄ±mladngÄ±na gÃ¶re constructor, demek ki aynÄ± anda LoginFormlaravelValidator yaratÄ±lacak 
                $app->make('Authority\Repo\Session\SessionInterface') // ve SessionInterface yaratÄ±lacak ? :/ yani LoginForm($param1, $param2) ÅŸeklinde o yÃ¼zden iÃ§ini doldurmuÅŸ?
            );
        });
        
        
$app->bind('benzinlik',$app)
{
    return new ShellBenzinlik();
} 


//LoginForm.php nin constructor u
	public function __construct(ValidableInterface $validator, SessionInterface $session) //demek ki doÄŸru anlamÄ±sÄ±m
	{
		$this->validator = $validator;
		$this->session = $session;
	}




//Burda tanÄ±mladÄ±ÄŸÄ±n ÅŸeyi kullanmak iÃ§in

$benzinlik = $app->make('benzinlik'); 
    
