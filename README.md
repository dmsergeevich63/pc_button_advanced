# pc_button_advanced
Это проект для платы esp32/8266 встроенной в компьютер для управлением лампами Yelight или Xiaomi с помощью кнопки включения или любой другой ненужной кнопки. Также имеется версия кода с приложеним blynk для включения ПК через Wake-on-LAN(для этого должны быть активированы опции в BIOS USB PowerOn и Wake-on-LAN)
Функции кнопки:
  * Простое нажатие - вкл/выкл основной лампы
  * Удерживание n секунд включает в основной лампе:
   * * 0,1 секунды - фоновую подсветку в режиме плавного смены цветов
   * * 3 секунд - лунную подсветку
   * * 7 секунд - дневуную подсветку на минимальной яркости
   * * 9 секунд - дневуную подсветку на максимальной яркости
   * Двойное нажатие вкл/выкл вторую лампу
   
Особенно хочется отметить команду плавной смены цветов это то, чего я не видел в других репозитория:
   ```CPP
   const char*  set_bg_start_cf = "{\"id\":1,\"method\":\"bg_start_cf\",\"params\":[0,0,\"10000,1,255,100,10000,1,65280,100,10000,1,16711680,100\"]}\r\n";
   ```
 Эта команда написана с помощью библиотеки *** и перехвачена с помощью Wireshark!
     
   
   Для использования требуется заполнить следующие поля:
   
   ```CPP
   const char* ssid = ""; //Enter SSID
const char* password = ""; //Enter Password
```
   ```CPP
   const char* H0 = "192.168.0.85"; // YLXD50YL //основная лампа
const char* H2 = "192.168.0.226"; //bslamp //вторая лампа
```

  
  
