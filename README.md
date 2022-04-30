
### <a name="1"></a> Araştırma Projesi 1

- Lateinit neden kullanıyoruz?
- Lateinit kullanımından bahseder misiniz?
- Lateinit için bir örnek kullanım gösterir misiniz ?

#### <a name="1"></a> Cevaplar

Lateinit geç başlatma anlamına gelir.Eğer değer atamayı hemen yapmak istemiyorsak, daha sonra başlatmak istiyorsak ve bu değişkeni kullanacğımız garanti
ise lateinit kullanıyoruz. Daha sonra başlatma işlemini android geliştirmesinde onCreate, onResume gibi olaylarla yapabiliriz ve bu daha sonra başlatma
özelliğinden dolayı lateinit ile val kullanamayız, var kullanabiliriz. Aynı zamanda lateinit sadece null olmayan veri türlerine izin verir yani değerin gelecekte başlatılacağının sözüdür.




    private lateinit var switch: Switch
    private lateinit var imageView:ImageView
    private lateinit var textView: TextView
    private lateinit var button: Button

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
        switch=findViewById(R.id.switch1)
        imageView=findViewById(R.id.imageView3)
        button=findViewById(R.id.button)
        textView=findViewById(R.id.textView)

        switch.setOnCheckedChangeListener { buttonView, isChecked ->
            if(isChecked)
                imageView.setImageResource(R.drawable.aciklamba)
            else
                imageView.setImageResource(R.drawable.kapalilamba)

        }
 }
 }

 ### <a name="2"></a> Araştırma Projesi 2


- Layout dizini içinde xml dosyalarımız için kullandığımız namespace nedir ?
- Neden kullanılmaktadır ?
- Nasıl kullanılmalıdır ?
- Bir adet Tools (tools namespace) attribute kullanımını gösterir misiniz ? 

#### <a name="1"></a> Cevaplar



Tools Namespace

Tools namespace ile uygulama geliştirirken tasarım tarafında yapılan değişikliklerin çıktısını uygulamayı çalıştırmadan 
anında görebiliz.Kullanabilmek için ise xmlns:tools="http://schemas.android.com/tools" tanımlaması yapmamız gerekir.


<TextView     
    android:layout_width="match_parent"                      
    android:layout_height="wrap_content"     
    tools:text="Lorem text" /

<ImageView     
    android:layout_width="wrap_content"    
    android:layout_height="wrap_content"     
    tools:src="@drawable/sampleImg" /
    
 ### <a name="2"></a> Araştırma Projesi 3
 
- Font family dosyası nasıl oluşturulup kullanıyoruz?
- Neden belirttiğiniz şekilde kullanımı tercih ediyoruz?

#### <a name="1"></a> Cevaplar

res altında directory ile font oluşturuyoruz. Daha sonra belirlediğimiz fontları içine atıyoruz ve font içinde bir xml dosyası oluşturuyoruz. Bu xml dosyası içinde
de fontumuzun özelliklerini belirliyoruz(fontweight:400,fontstyle:"italic" gibi). Bu kullanımı tercih etmemizin sebebi ise kendi fontumuzu oluşturup projemizde rahatlıkla kullanabilmek. 

![font-family](https://user-images.githubusercontent.com/96207103/166081287-2ba90b19-9509-4c63-9edf-3c87cb9ac035.png)

Activity_main içerisinde ise şu şekilde kullanırız:

![Adsız](https://user-images.githubusercontent.com/96207103/166081861-d8a36412-dd9f-4943-9a03-7460e5c4a7db.png)

 ### <a name="2"></a> Araştırma Projesi 4
 
 - Property Animation ile ilgili olarak objectAnimator ile animator arasındaki farkı kısaca açıklayınız

#### <a name="1"></a> Cevaplar

- objectanimator belirli bir süre boyunca bir nesnenin belirli bir özelliğini canlandırır(Arka plan rengi veya alfa değeri gibi bileşenin özelliklerini belirli bir süre boyunca değiştirir).

- animator belirli bir süre boyunca bir animasyon gerçekleştirir ve bir value animatörünü temsil eder

