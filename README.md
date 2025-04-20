# RHYX-M21-45
RHYX M21-45

 متاسفانه بسیاری فروشندگان داخلی ماژول ESP32-cam را همراه با دوربین OV2640 عرضه نمیکنند هر چند که در مشخصات فروش ماژول دوربین OV2640 رو ارائه میدهند 

 دوربین RHYX M21-45 یک دوربین با رزولیشن پایین هست و 2 مگا پیکسل هم نیست که متاسفانه با گشتن در اینترنت بسیاری با این دروبین مشکل داشتند و حتی DataSheet و رفرنسی برای این دوربین پیدا نکردم 

 که متاسفانه  خودم تجربه بدی ازش دارم که حتی در راه اندازی آن به مشکل برخوردم 

تجربه شخصی من با این دوربین 

فقط یک تصویر با رزولیشن ثابت  رو نشون داد که نمیتوان رزولیشن رو تغییر داد
	 
امکان تغییر Quality  وجود ندارد
		 
امکان تغییر Brightness وجود ندارد

امکان تغییر Contrast وجود ندارد

امکان تغییر Saturation وجود ندارد

امکن تغییر Special Effect وجود ندارد

امکان تغییر AWB وجود ندارد

امکان تغییر WB Mode وجود ندارد	

با فشردن دکمه AEC SENSOR تصویر بصورت اینه وار تغییر پیدا میکند

امکان تغییر AEC DSP وجود ندارد

امکان تغییر AE Level وجود ندارد

امکان تغییر AGC وجود ندارد

امکان تغییر Gain Ceiling وجود ندارد

امکان تغییر BPC وجود ندارد

امکان تغییر WPC وجود ندارد

امکان تغییر Raw GMA وجود ندارد

امکان تغییر Lens Correction وجود ندارد	

قابلیت H-Mirror اجرا شد

امکان تغییر V-Flip وجود ندارد و ب دکمه  AEC SENSOR قابل اجراست	

امکان تغییر DCW (Downsize EN) وجود ندارد

قبلیت LED Intensity اجرا شد که ربطی به دوربین نداشت

امکان تغییر Color Bar وجود ندارد

قابلیت Face Detection اجرا شد که باز هم ربطی به دوربین ندارد



نحوه راه اندازی RHYX M21-45 در اردینو Ardiniuo    
در بخش     
// ===================
// Select camera model
// ===================
```
#define CAMERA_MODEL_AI_THINKER  // Has PSRAM
```
انتخاب شود 

در بخش 

camera_config_t config;

کدهای زیر رو کپی پیست کنید و یا بصورت زیر تغییر دهید
```C
 camera_config_t config;

 config.ledc_channel = LEDC_CHANNEL_0;

 config.ledc_timer = LEDC_TIMER_0;  

config.pin_d0 = Y2_GPIO_NUM;

config.pin_d1 = Y3_GPIO_NUM;

config.pin_d2 = Y4_GPIO_NUM;

config.pin_d3 = Y5_GPIO_NUM;

config.pin_d4 = Y6_GPIO_NUM;

config.pin_d5 = Y7_GPIO_NUM;

config.pin_d6 = Y8_GPIO_NUM;

config.pin_d7 = Y9_GPIO_NUM;

config.pin_xclk = XCLK_GPIO_NUM;

config.pin_pclk = PCLK_GPIO_NUM;

config.pin_vsync = VSYNC_GPIO_NUM;

config.pin_href = HREF_GPIO_NUM;

config.pin_sccb_sda = SIOD_GPIO_NUM;

config.pin_sccb_scl = SIOC_GPIO_NUM;

config.pin_pwdn = PWDN_GPIO_NUM;

config.pin_reset = RESET_GPIO_NUM;

//config.xclk_freq_hz = 20000000; high

config.xclk_freq_hz = 10000000; 

config.pixel_format = PIXFORMAT_RGB565;

config.frame_size = FRAMESIZE_QQVGA; 

//config.frame_size = FRAMESIZE_QVGA;

//config.frame_size = FRAMESIZE_VGA;

config.jpeg_quality = 10; 

config.fb_count = 2;

config.grab_mode = CAMERA_GRAB_LATEST;

config.fb_location = CAMERA_FB_IN_PSRAM;
```

