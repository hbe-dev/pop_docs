<h1> Pop </h1>
The code to import the whole of Pop Library : 

```python
from pop import *
```
<br>

<!-- # Class & Method Description-->
<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Out**    

> Output device controlled throught GPIO

<h5>&emsp;Initialization</h5>

&emsp; `Out(n)` : Out Object<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Output Device

<h5>&emsp;Methods</h5>

&emsp; `on()` : Set GPIO Connected to Output Device to HIGH  
&emsp; `off()` : Set GPIO Connected to Output Device to LOW   

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Led**    
> LEDs are controlled via GPIO    

<h5>&emsp;Initialization</h5>   

&emsp;`Led(n)` : Led Object inheriting from Out Class<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the LED   

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Leds**    
> LEDs are controlled via GPIO    

<h5>&emsp;Initialization</h5>   

&emsp;`Leds(n)` : Leds Object inheriting from Led Class<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : list Number defined board config Connected to the LED  

<h5>&emsp;Methods</h5>   

&emsp;`allOn()` : Set all GPIO Connected to Output Device to HIGH    
&emsp;`allOff()` : Set all GPIO Connected to Output Device to LOW    

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Input**    
> Read the Input Device through GPIO    

<h5>&emsp;Initialization</h5> 

&emsp;`Input(n,activeHigh=Ture)` : Input Object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Input Device    
&emsp;&emsp;&emsp;`activeHigh` : Used to check if the Input Device is HIGH when pressed , Default `True`    

<h5>&emsp;Definitions</h5>

&emsp;`FALLING` : Detect Falling Edge    
&emsp;`RISING` : Detect Rising Edge    
&emsp;`BOTH` : Detect Both Side    

<h5>&emsp;Methods</h5>  

&emsp;`read()` : Read the Input Device Status    
&emsp;`setCallback(func,param=None,type=BOTH)` : Set Callback Function When Detect Edge<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Arguments passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Call condition of Callback function , Default BOTH  

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Switch**    
> Read the switch status through GPIO    

<h5>&emsp;Initialization</h5>   

&emsp;`Switch(n)` : Switch Object inheriting from Input Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Switch    

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Switches**    
> Read the switch status through GPIO    

<h5>&emsp;Initialization</h5>

&emsp;`Switches(n)` : Switch Object inheriting from Input Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : list Number defined board config Connected to the Switch    

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **SpiAdc**    
> adc chip control through spi interface    

<h5>&emsp;Initialization</h5>   

&emsp;`SpiAdc(channel, device=0, bus=0, speed=1000000)` : SpiAdc object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)  
			
<h5>&emsp;Definitions</h5>  

&emsp;`TYPE_AVERAGE` : Average data based on sampling count    
&emsp;`TYPE_NORMAL` : Unaveraged raw data    
&emsp;`MODE_FULL` : Call Callback function always    
&emsp;`MODE_INCLUSIVE` : If data is in arange(max, min), call Callback function    
&emsp;`MODE_EXCLUSIVE` : If data is over arange, call Callback function    

<h5>&emsp;Methods</h5>   

&emsp;`getSample()` : Get Sampling Count    
&emsp;`read()` : Read Data from Device (Raw Type)    
&emsp;`readAverage()` : Read Average Data from Device    
&emsp;`run()` : Read data and call Callback function according to mode  
&emsp;`setChipSelect(cs)` : Set SPI Chip Select PIN<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`cs` : Chipselect GPIO for SPI Interface

&emsp;`setSample(sample)` : Set Sampling Count<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sample` : Sampling count


&emsp;`readVolt(ref=3.3,max=3020.0)` : Read Data from Device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference Voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data


&emsp;`readVoltAverage(ref=3.3,max=3020.0)` : Read Data from Device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference Voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data

&emsp;`setCallback(func,param=None,type=TYPE_AVERAGE,mode=MODE_FULL,min=0,max=ADC_MAX)` <br>&emsp;: Set up callback function for automatic data read<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Arguments passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Data Read Type , Default TYPE_AVERAGE    
&emsp;&emsp;&emsp;`mode` : Select Mode , Default MODE_FULL    
&emsp;&emsp;&emsp;`min` : analog data minimum , Default 0    
&emsp;&emsp;&emsp;`max` : analog data maximum , Default 4095 (MCP3208 12bit ADC Chip)

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Psd**    
> Distance measurement using PSD sensor    

<h5>&emsp;Initialization</h5>   

&emsp;`Psd(channel=-1, device=0, bus=0, speed=1000000)` : PSD object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>  

&emsp;`calcDist(val,calibration=1.1)` : Calculate distance value from raw data    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ADC Raw Data    
&emsp;&emsp;&emsp;`calibration` : Calibration Value, Default 1.1    
			
---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **CDS**  
> Light measurement using CDS sensor    

<h5>&emsp;Initialization</h5>   

&emsp;`Cds(channel=-1, device=0, bus=0, speed=1000000)` : Cds object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
<h5>&emsp;Methods</h5>  

&emsp;`readAverage()` : Read lux data from device and calibration function  
&emsp;`setCalibrationPseudoLx(func)` : Set calibration function<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Calibration function

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Sound**    
> Ambient sound measurement using Sound sensor    

<h5>&emsp;Initialization</h5>   

&emsp;`Sound(channel=-1, device=0, bus=0, speed=1000000)` : Sound object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Vr**    
> Voltage measurement with variable resistor    

<h5>&emsp;Initialization</h5>   

&emsp;`Vr(channel=-1, device=0, bus=0, speed=1000000)` : Vr object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Potentiometer**    
> Voltage measurement with variable resistor    

<h5>&emsp;Initialization</h5>

&emsp;`Potentiometer(channel=-1, device=0, bus=0, speed=1000000)` <br>&emsp;: Potentiometer object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>   
  
&emsp;`readAverage()` : return level from range table   
&emsp;`getRangeTable()` : return range table  
&emsp;`setRangeTable(table)` : Set potentiometer range table<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`table` : Table with 10 elements    
&emsp;&emsp;&emsp;&emsp;ex) [48, 300, 700, 1090, 1540, 1945, 2320, 2715, 2980, 3040]

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **PiezoBuzzer**    
> PiezoBuzzer controlled via Software PWM  

<h5>&emsp;Initialization</h5>   

&emsp;`PiezoBuzzer(n)` : PiezoBuzzer object inheriting from PopThread<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the PiezoBuzzer defined board setting or Can setting manually    

<h5>&emsp;Methods</h5>   

&emsp;`isPlay()` : return play status  
&emsp;`getTempo()` : Get tempo value  
&emsp;`setTempo(n)` : Set tempo value<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : Value to be set to tempo

&emsp;`tone(scale,pitch,duration)` : Play a note on piezo buzzer during duration value    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`scale` : Scale value to play on piezo buzzer (int type)    
&emsp;&emsp;&emsp;`pitch` : Pitch value to play on piezo buzzer. 'Do' is 1, 'Do♯' is 2, 'Re' is 3 and 'Si' is 12    
&emsp;&emsp;&emsp;`duration` : Tone is playing during duration value

&emsp;`rest(duration)` : Stop to play piezo buzzer    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`duration` : The duration of the stopping

&emsp;`play(sheet)` : play music by sheet<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sheet` : list [[scale],[pitch],[duration]]

---

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Oled**    
> Oled Controlled vi I2C Interface    

<h5>&emsp;Initialization</h5>  

&emsp;`Oled( addr=OLED_ADDR, type=OLED_NONE_TYPE, automode=True)` <br>&emsp;: Oled object inheriting from I2C Class (I2c Slave Address -> 0x3c). This method calls init(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : OLED I2C ADDR.default 0x3c    
&emsp;&emsp;&emsp;`type` : OLED Type. difined board config    
&emsp;&emsp;&emsp;`automode` : select automode. default `True`    

&emsp;**Definitions**    
&emsp;`OLED_SSD1306_I2C_128x32` : OLED device type number, if model name is 'SSD1306', select this type    
&emsp;`OLED_SH1106_I2C_128x64` : OLED device type number, if model name is 'SSH1106', select this type    
&emsp;`BLACK` : In OLED, you can use only 2 colors. One of them is black. Numeric value is 0    
&emsp;`WHITE` : Another of them is white. Numeric value is 1    

<h5>&emsp;Methods</h5>

&emsp;`width()` : Retun widht of OLED    
&emsp;`height()` : Return height of OLED   
&emsp;`display()` : Display buffer data on OLED    
&emsp;`clearDisplay()` : Clear the data on OLED    
&emsp;`init(type=OLED_SH1106_I2C_128x64)` <br>&emsp;: Initialize OLED and set width/height of OLED. This method calls setTextSize(), setTextColor(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`type` : Select OLED type

&emsp;`print(string)` : Print a string on OLED. Replace '\n' to New-Line    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`string`: The string to print on OLED

&emsp;`drawCircle(x0, y0, r, color)` : Draw a circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)    

&emsp;`fillCircle(x0, y0, r, color)` : Draw a filled circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)   

&emsp;`drawLine(x0, y0, x1, y1, color)` : Draw a line on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`x1` : End point of x-axis    
&emsp;&emsp;&emsp;`y1` : End point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a line. BLACK(0) or WHITE(1)    

&emsp;`drawRect(x, y, w, h, color)` : Draw a rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)   

&emsp;`fillRect(x, y, w, h, color)` : Draw a filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)    

&emsp;`drawVerticalBargraph(x, y, w, h, color, percent)` : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the graph    
&emsp;&emsp;&emsp;`h` : Full height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always up-side    

&emsp;`drawHorizontalBargraph(x, y, w, h, color, percent)` : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Full width of the graph    
&emsp;&emsp;&emsp;`h` : Height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always right-side    

&emsp;`drawRoundRect(x, y, w, h, r, color)` : Draw a rounded rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph. BLACK(0) or WHITE(1)   

&emsp;`fillRoundRect(x, y, w, h, r, color)` : Draw a rounded and filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph BLACK(0) or WHITE(1)   

&emsp;`drawTriangle(x0, y0, x1, y1, x2, y2, color)` : Draw a triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : First point of x-axis    
&emsp;&emsp;&emsp;`y0` : First point of y-axis    
&emsp;&emsp;&emsp;`x1` : Second point of x-axis    
&emsp;&emsp;&emsp;`y1` : Second point of y-axis    
&emsp;&emsp;&emsp;`x2` : Third point of x-axis    
&emsp;&emsp;&emsp;`y2` : Third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)    

&emsp;`fillTriangle(x0, y0, x1, y1, x2, y2, color)` : Draw a filled triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : First point of x-axis    
&emsp;&emsp;&emsp;`y0` : First point of y-axis    
&emsp;&emsp;&emsp;`x1` : Second point of x-axis    
&emsp;&emsp;&emsp;`y1` : Second point of y-axis    
&emsp;&emsp;&emsp;`x2` : Third point of x-axis    
&emsp;&emsp;&emsp;`y2` : Third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)
   
&emsp;`drawChar(x, y, c, color, bg, size)` : Draw a character on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of x-axis    
&emsp;&emsp;&emsp;`c` : A character to be drawn    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`bg` : The background of a character. Background size is 6 * 8 * textsize    
&emsp;&emsp;&emsp;`size` : Pixel size of charactor strock. Default is 1   

&emsp;`drawBitmap(x, y, bitmap, w, h, color)` : Draw a bitmap data on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`bitmap` : A two dimensional array which consist of 0 and 1, 0 is black and 1 is white    
&emsp;&emsp;&emsp;`w` : Width of bitmap data    
&emsp;&emsp;&emsp;`h` : Height of bitmap data    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)   

&emsp;`setCursor(x, y)` : Set the cursor on OLED, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis point of cursor    
&emsp;&emsp;&emsp;`y` : y-axis point of cursor 

&emsp;`setTextSize(s)` : Set text size, This value is used in write()    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`s` : Pixel size of charactor strock. Default is 1 

&emsp;`setTextColor(c)` : Set text color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)   

&emsp;`setTextColorWithBg(c, b)` : Set text color and background color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`b` : Background color value. BLACK(0) or WHITE(1) 

&emsp;`drawPixel(x, y, color)` : Draw a dot on OLED    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : The point of a dot    
&emsp;&emsp;&emsp;`y` : The point of a dot    
&emsp;&emsp;&emsp;`color` : The color of a dot    

&emsp;`setBrightness(Brightness)` : Set brightness of OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`Brightness` : Brightness value to be set   

&emsp;`invertDisplay(i)` : Change display mode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`i` : If i is `True`, dispaly mode is Inverse mode but if i is False, display mode is Normal mode. In Inverse mode, 0 is white and 1 is black    

&emsp;`istartscrollright(start, stop)` <br>&emsp;: Scroll the screen in the row-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling   

&emsp;`startscrollleft(start, stop)` <br>&emsp;: Scroll the screen in the row-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;`startscrolldiagright(start, stop)` <br>&emsp;: Scroll the screen in the column-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;`startscrolldiagleft(start, stop)` <br>&emsp;: Scroll the screen in the column-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;`stopscroll()` : Stop scrolling the screen    

&emsp;`write(c)` : Write the character at location of cursor on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : The character to be written   

&emsp;`setAutomode(automode)` : set automode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    

<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Gesture**    

> Apds9960 Controlled via I2C Interface    

<h5>&emsp;Initialization</h5>   

&emsp;`Gesture(addr=APDS9960_ADDR)` : Gesture object inheriting from I2C Class (I2c Slave Address -> 0x39)    
	
<h5>&emsp;Methods</h5>   

&emsp;`isAvailable()` : return Gesture detection status(1). Wait until Gesture is detected    
&emsp;`read()` : return number as Gesture status.  
&emsp;&emsp;**Return**    
&emsp;&emsp;&emsp;`0` : "None" , `1` : "Left", `2` : "Right", `3` : "Up", `4` : "Down", `5`: "Near", `6` : "Far"    

&emsp;`readStr()` : return String as Gesture status.    
&emsp;&emsp;**Return**  
&emsp;&emsp;&emsp;"None" , "Left", "Right", "Up", "Down", "Near", "Far"    
		
<h5>&emsp;Inner Class</h5>  

&emsp;**Light**    
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Light()` : Light object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`read()` : return light value    

&emsp;**Color**    
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Color()` : Color object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`readRed()` : return Red value    
&emsp;&emsp;`readGreen()` : return Green value    
&emsp;&emsp;`readBlue()` : return Blue value

&emsp;**Proximity**  
&emsp;&emsp;**Initialization**<br>
&emsp;&emsp;`Proximity()` : Proximity object  <br><br>
&emsp;&emsp;**Methods**<br>
&emsp;&emsp;`read()` : return Proximity value    
	
<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **PixelDisplay**    
> Pixel Display controlled via Hardware PWM  
  
<h5>&emsp;Initialization</h5> 

&emsp;`PixelDisplay(width=8, height=8, gpio=-1, type=GRB, dma=10, automode=True, debug=False)` <br>&emsp;: PixelDisplay object    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`width` : Number of Pixel width    
&emsp;&emsp;&emsp;`height` : Number of Pixel height    
&emsp;&emsp;&emsp;`automode` : automode setting. `True` or `False`    

<h5>&emsp;Methods</h5>  

&emsp;`display()` : send command from buffer. when Automode `False` use    
&emsp;`getRGBType()` : getRGBType    
&emsp;`RGBtoHEX(color_arr)` : convert RGB list data to HEX  
&emsp;`clear()` : clear PixelDisplay  
&emsp;`rainbow()` : display rainbow color on Pixel Display  
&emsp;`fill(color_arr)` : Fill PixelDisplay to one color    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color_arr` : A color to be filled. Type is list of [R, G, B]  
   
&emsp;`setColor(x, y, color_arr)` : set PixelDisplay color_arr on x,y    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis    
&emsp;&emsp;&emsp;`color_arr` : A color to be set. Type is list of [R, G, B] or HEX (0xRRGGBB)    

&emsp;`getColor(x, y)` : return color on x,y as INT type    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis 

&emsp;`setAutomode(automode)` : set automode. default `True`. if `False` set, shuld use display()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    
   
&emsp;`setBrightness(brightness)` : set Brightness    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`brightness` : brightness (0~255)    
  
&emsp;`setColorInvert(invert)` : inver color. default `False`    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`invert`  
&emsp;&emsp;&emsp;&emsp;`True` : input (255,0,0) -> (0,255,255)    
&emsp;&emsp;&emsp;&emsp;`False` : input (255,0,0) -> (255,0,0)    

