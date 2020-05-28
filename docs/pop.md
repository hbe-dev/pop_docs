<h1> Pop </h1>
The code to import the whole of Pop Library : 

```python
from pop import *
```
<br>

<!-- # Class & Method Description-->
<hr/>

## <span class="title">Class</span> <span class="title_accent">**Out**</span>    

<blockquote class="desc"> Output device controlled throught GPIO</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Out(n)</code> : Out Object<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Output Device

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">on()</code> : Set GPIO Connected to Output Device to HIGH  
&emsp;<code class="code_accent">off()</code> : Set GPIO Connected to Output Device to LOW   

---

## <span class="title">Class</span> <span class="title_accent">**Led**</span>    
<blockquote class="desc">LEDs are controlled via GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Led(n)</code> : Led Object inheriting from Out Class<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the LED   

---

## <span class="title">Class</span> <span class="title_accent">**Leds**</span>    
<blockquote class="desc">LEDs are controlled via GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Leds(n)</code> : Leds Object inheriting from Led Class<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : list Number defined board config Connected to the LED  

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">allOn()</code> : Set all GPIO Connected to Output Device to HIGH    
&emsp;<code class="code_accent">allOff()</code> : Set all GPIO Connected to Output Device to LOW    

---

## <span class="title">Class</span> <span class="title_accent">**Fan**</span>    
<blockquote class="desc">Fan is controlled via GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Fan(n)</code> : Fan Object inheriting from Out Class<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Fan   

---

## <span class="title">Class</span> <span class="title_accent">**Input**</span>    
<blockquote class="desc">Read the Input Device through GPIO</blockquote>    

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Input(n,activeHigh=Ture)</code> : Input Object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Input Device    
&emsp;&emsp;&emsp;`activeHigh` : Used to check if the Input Device is HIGH when pressed , Default `True`    

<h5>&emsp;Definitions</h5>

&emsp;<code class="code_accent">FALLING</code> : Detect Falling Edge    
&emsp;<code class="code_accent">RISING</code> : Detect Rising Edge    
&emsp;<code class="code_accent">BOTH</code> : Detect Both Side    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">read()</code> : Read the Input Device Status    
&emsp;<code class="code_accent">setCallback(func,param=None,type=BOTH)</code> : Set Callback Function When Detect Edge<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Arguments passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Call condition of Callback function , Default BOTH  

---

## <span class="title">Class</span> <span class="title_accent">**Switch**</span>    
<blockquote class="desc">Read the switch status through GPIO</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Switch(n)</code> : Switch Object inheriting from Input Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Switch    

---

## <span class="title">Class</span> <span class="title_accent">**Switches**</span>    
<blockquote class="desc">Read the switch status through GPIO</blockquote>    

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Switches(n)</code> : Switch Object inheriting from Input Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : list Number defined board config Connected to the Switch    

---

## <span class="title">Class</span> <span class="title_accent">**Pir**</span>    
<blockquote class="desc">Pir</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Pir(n)</code> : Pir Object inheriting from Input Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the Pir 

---

## <span class="title">Class</span> <span class="title_accent">**SpiAdc**</span>    
<blockquote class="desc">adc chip control through spi interface</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">SpiAdc(channel, device=0, bus=0, speed=1000000)</code> : SpiAdc object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)  
			
<h5>&emsp;Definitions</h5>  

&emsp;<code class="code_accent">TYPE_AVERAGE</code> : Average data based on sampling count    
&emsp;<code class="code_accent">TYPE_NORMAL</code> : Unaveraged raw data    
&emsp;<code class="code_accent">MODE_FULL</code> : Call Callback function always    
&emsp;<code class="code_accent">MODE_INCLUSIVE</code> : If data is in arange(max, min), call Callback function    
&emsp;<code class="code_accent">MODE_EXCLUSIVE</code> : If data is over arange, call Callback function    

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">getSample()</code> : Get Sampling Count    
&emsp;<code class="code_accent">read()</code> : Read Data from Device (Raw Type)    
&emsp;<code class="code_accent">readAverage()</code> : Read Average Data from Device    
&emsp;<code class="code_accent">run()</code> : Read data and call Callback function according to mode  
&emsp;<code class="code_accent">setChipSelect(cs)</code> : Set SPI Chip Select PIN<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`cs` : Chipselect GPIO for SPI Interface

&emsp;<code class="code_accent">setSample(sample)</code> : Set Sampling Count<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sample` : Sampling count


&emsp;<code class="code_accent">readVolt(ref=3.3,max=3020.0)</code> : Read Data from Device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference Voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data


&emsp;<code class="code_accent">readVoltAverage(ref=3.3,max=3020.0)</code> : Read Data from Device (Voltage Type)<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`ref` : Reference Voltage    
&emsp;&emsp;&emsp;`max` : Maximum value of raw data

&emsp;<code class="code_accent">setCallback(func,param=None,type=TYPE_AVERAGE,mode=MODE_FULL,min=0,max=ADC_MAX)</code> <br>&emsp;: Set up callback function for automatic data read<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Function to use when calling Callback    
&emsp;&emsp;&emsp;`param` : Arguments passed to the Callback function , Default None    
&emsp;&emsp;&emsp;`type` : Data Read Type , Default TYPE_AVERAGE    
&emsp;&emsp;&emsp;`mode` : Select Mode , Default MODE_FULL    
&emsp;&emsp;&emsp;`min` : analog data minimum , Default 0    
&emsp;&emsp;&emsp;`max` : analog data maximum , Default 4095 (MCP3208 12bit ADC Chip)

---

## <span class="title">Class</span> <span class="title_accent">**Psd**</span>    
<blockquote class="desc">Distance measurement using PSD sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Psd(channel=-1, device=0, bus=0, speed=1000000)</code> : PSD object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">calcDist(val,calibration=1.1)</code> : Calculate distance value from raw data    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ADC Raw Data    
&emsp;&emsp;&emsp;`calibration` : Calibration Value, Default 1.1    
			
---

## <span class="title">Class</span> <span class="title_accent">**CDS**</span>  
<blockquote class="desc">Light measurement using CDS sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Cds(channel=-1, device=0, bus=0, speed=1000000)</code> : Cds object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">readAverage()</code> : Read lux data from device and calibration function  
&emsp;<code class="code_accent">setCalibrationPseudoLx(func)</code> : Set calibration function<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : Calibration function

---

## <span class="title">Class</span> <span class="title_accent">**Gas**</span>    
<blockquote class="desc">Gas</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Gas(channel=-1, device=0, bus=0, speed=1000000)</code> : Gas object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)       
			
<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">calibration(rl=4.7, clean=1)</code> : return calibration R0(using calculation gas value) value <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`rl` : register in circuit   
&emsp;&emsp;&emsp;`clean` : value in clean air

&emsp;<code class="code_accent">setPropanCurve(x, y, inclination)</code> : setPropanCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis of PropanCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis of PropanCurve in datasheet  
&emsp;&emsp;&emsp;`inclination` : inclination of PropanCurve in datasheet    

&emsp;<code class="code_accent">setMethanCurve(x, y, inclination)</code> : setMethanCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis of PropanCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis of PropanCurve in datasheet    
&emsp;&emsp;&emsp;`inclination` : inclination of PropanCurve in datasheet    

&emsp;<code class="code_accent">setEthanolCurve(x, y, inclination)</code> : setEthanolCurve<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : any x-axis of PropanCurve in datasheet    
&emsp;&emsp;&emsp;`y` : any y-axis of PropanCurve in datasheet    
&emsp;&emsp;&emsp;`inclination` : inclination of PropanCurve in datasheet    

&emsp;<code class="code_accent">calcPropan(val)</code> : return Propan Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value     

&emsp;<code class="code_accent">calcMethan(val)</code> : return Methan Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    

&emsp;<code class="code_accent">calcEthanol(val)</code> : return Ethanol Gas value as ppm<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    

&emsp;<code class="code_accent">resistanceCalculation(val, rl=4.7)</code> : return resistance value<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : raw ADC value    
&emsp;&emsp;&emsp;`rl` : register in circuit     

---

## <span class="title">Class</span> <span class="title_accent">**Temperature**</span>    
<blockquote class="desc">Temperature object inheriting from SpiAdc Class</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Temperature(channel, device=0, bus=0, speed=1000000)</code> : Temperature object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)   
			
<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">calcTempC(val, cal=1309)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ...    
&emsp;&emsp;&emsp;`cal` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**Sound**</span>    
<blockquote class="desc">Ambient sound measurement using Sound sensor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Sound(channel=-1, device=0, bus=0, speed=1000000)</code> : Sound object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
---

## <span class="title">Class</span> <span class="title_accent">**Vr**</span>    
<blockquote class="desc">Voltage measurement with variable resistor</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Vr(channel=-1, device=0, bus=0, speed=1000000)</code> : Vr object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
---

## <span class="title">Class</span> <span class="title_accent">**Potentiometer**</span>    
<blockquote class="desc">Voltage measurement with variable resistor</blockquote>    

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Potentiometer(channel=-1, device=0, bus=0, speed=1000000)</code> <br>&emsp;: Potentiometer object inheriting from SpiAdc Class<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ADC Channel    
&emsp;&emsp;&emsp;`device` : SPI Interface Channel , Default 0 (in Raspberry Pi)    
&emsp;&emsp;&emsp;`bus` : Not Used..    
&emsp;&emsp;&emsp;`speed` : SPI Interface Clock Speed , Default 1000000(1MHz)    

<h5>&emsp;Methods</h5>   
  
&emsp;<code class="code_accent">readAverage()</code> : return level from range table   
&emsp;<code class="code_accent">getRangeTable()</code> : return range table  
&emsp;<code class="code_accent">setRangeTable(table)</code> : Set potentiometer range table<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`table` : Table with 10 elements    
&emsp;&emsp;&emsp;&emsp;ex) [48, 300, 700, 1090, 1540, 1945, 2320, 2715, 2980, 3040]

---

## <span class="title">Class</span> <span class="title_accent">**PiezoBuzzer**</span>    
<blockquote class="desc">PiezoBuzzer controlled via Software PWM</blockquote>  

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">PiezoBuzzer(n)</code> : PiezoBuzzer object inheriting from PopThread<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : GPIO Number Connected to the PiezoBuzzer defined board setting or Can setting manually    

<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">isPlay()</code> : return play status  
&emsp;<code class="code_accent">getTempo()</code> : Get tempo value  
&emsp;<code class="code_accent">setTempo(n)</code> : Set tempo value<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`n` : Value to be set to tempo

&emsp;<code class="code_accent">tone(scale,pitch,duration)</code> : Play a note on piezo buzzer during duration value    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`scale` : Scale value to play on piezo buzzer (int type)    
&emsp;&emsp;&emsp;`pitch` : Pitch value to play on piezo buzzer. 'Do' is 1, 'Do♯' is 2, 'Re' is 3 and 'Si' is 12    
&emsp;&emsp;&emsp;`duration` : Tone is playing during duration value

&emsp;<code class="code_accent">rest(duration)</code> : Stop to play piezo buzzer    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`duration` : The duration of the stopping

&emsp;<code class="code_accent">play(sheet)</code> : play music by sheet<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sheet` : list [[scale],[pitch],[duration]]

---

## <span class="title">Class</span> <span class="title_accent">**I2c**</span>    
<blockquote class="desc">I2c</blockquote>

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">I2c(addr, bus=1)</code> : I2c object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c Address    
&emsp;&emsp;&emsp;`bus` : I2c Interface bus. Default is 1    
			
<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">read()</code> : ...
&emsp;<code class="code_accent">readByte(reg)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    

&emsp;<code class="code_accent">readWord(reg)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    

&emsp;<code class="code_accent">readBlock(reg, length)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    
&emsp;&emsp;&emsp;`length` : ...    

&emsp;<code class="code_accent">write(data)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`data` : ...    

&emsp;<code class="code_accent">writeByte(reg, data)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    
&emsp;&emsp;&emsp;`data` : ...    

&emsp;<code class="code_accent">writeWord(reg, data)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    
&emsp;&emsp;&emsp;`data` : ...    

&emsp;<code class="code_accent">writeBlock(reg, data)</code> :....<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`reg` : ...    
&emsp;&emsp;&emsp;`data` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**TempHumi**</span>    
<blockquote class="desc">Temperature & Humidity</blockquote>

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">TempHumi()</code> : ... <br>
			
<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">readTemp()</code> : ...  
&emsp;<code class="code_accent">readHumi()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**Oled**</span>    
<blockquote class="desc">Oled Controlled vi I2C Interface</blockquote>    

<h5>&emsp;Initialization</h5>  

&emsp;<code class="code_accent">Oled( addr=OLED_ADDR, type=OLED_NONE_TYPE, automode=True)</code> <br>&emsp;: Oled object inheriting from I2C Class (I2c Slave Address -> 0x3c). This method calls init(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : OLED I2C ADDR.default 0x3c    
&emsp;&emsp;&emsp;`type` : OLED Type. difined board config    
&emsp;&emsp;&emsp;`automode` : select automode. default `True`    

&emsp;**Definitions**    
&emsp;<code class="code_accent">OLED_SSD1306_I2C_128x32</code> : OLED device type number, if model name is 'SSD1306', select this type    
&emsp;<code class="code_accent">OLED_SH1106_I2C_128x64</code> : OLED device type number, if model name is 'SSH1106', select this type    
&emsp;<code class="code_accent">BLACK</code> : In OLED, you can use only 2 colors. One of them is black. Numeric value is 0    
&emsp;<code class="code_accent">WHITE</code> : Another of them is white. Numeric value is 1    

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">width()</code> : Retun widht of OLED    
&emsp;<code class="code_accent">height()</code> : Return height of OLED   
&emsp;<code class="code_accent">display()</code> : Display buffer data on OLED    
&emsp;<code class="code_accent">clearDisplay()</code> : Clear the data on OLED    
&emsp;<code class="code_accent">init(type=OLED_SH1106_I2C_128x64)</code> <br>&emsp;: Initialize OLED and set width/height of OLED. This method calls setTextSize(), setTextColor(), clearDisplay()    <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`type` : Select OLED type

&emsp;<code class="code_accent">print(string)</code> : Print a string on OLED. Replace '\n' to New-Line    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`string`: The string to print on OLED

&emsp;<code class="code_accent">drawCircle(x0, y0, r, color)</code> : Draw a circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">fillCircle(x0, y0, r, color)</code> : Draw a filled circle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`r` : Radious of the circle    
&emsp;&emsp;&emsp;`color` : The color of a circle. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">drawLine(x0, y0, x1, y1, color)</code> : Draw a line on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : Start point of x-axis    
&emsp;&emsp;&emsp;`y0` : Start point of y-axis    
&emsp;&emsp;&emsp;`x1` : End point of x-axis    
&emsp;&emsp;&emsp;`y1` : End point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a line. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">drawRect(x, y, w, h, color)</code> : Draw a rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">fillRect(x, y, w, h, color)</code> : Draw a filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rectangle    
&emsp;&emsp;&emsp;`color` : The color of a rectangle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">drawVerticalBargraph(x, y, w, h, color, percent)</code> : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the graph    
&emsp;&emsp;&emsp;`h` : Full height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always up-side    

&emsp;<code class="code_accent">drawHorizontalBargraph(x, y, w, h, color, percent)</code> : Draw a graph on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Full width of the graph    
&emsp;&emsp;&emsp;`h` : Height of the graph    
&emsp;&emsp;&emsp;`color` : The color of the graph. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`percent` : The percentage of a graph. The direction of graph is always right-side    

&emsp;<code class="code_accent">drawRoundRect(x, y, w, h, r, color)</code> : Draw a rounded rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">fillRoundRect(x, y, w, h, r, color)</code> : Draw a rounded and filled rectangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`w` : Width of the rounded rectangle    
&emsp;&emsp;&emsp;`h` : Height of the rounded rectangle    
&emsp;&emsp;&emsp;`r` : Curvature of edge of the rounded rectangle    
&emsp;&emsp;&emsp;`color` : The color of a graph BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">drawTriangle(x0, y0, x1, y1, x2, y2, color)</code> : Draw a triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : First point of x-axis    
&emsp;&emsp;&emsp;`y0` : First point of y-axis    
&emsp;&emsp;&emsp;`x1` : Second point of x-axis    
&emsp;&emsp;&emsp;`y1` : Second point of y-axis    
&emsp;&emsp;&emsp;`x2` : Third point of x-axis    
&emsp;&emsp;&emsp;`y2` : Third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)    

&emsp;<code class="code_accent">fillTriangle(x0, y0, x1, y1, x2, y2, color)</code> : Draw a filled triangle on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x0` : First point of x-axis    
&emsp;&emsp;&emsp;`y0` : First point of y-axis    
&emsp;&emsp;&emsp;`x1` : Second point of x-axis    
&emsp;&emsp;&emsp;`y1` : Second point of y-axis    
&emsp;&emsp;&emsp;`x2` : Third point of x-axis    
&emsp;&emsp;&emsp;`y2` : Third point of y-axis    
&emsp;&emsp;&emsp;`color` : The color of a triangle. BLACK(0) or WHITE(1)
   
&emsp;<code class="code_accent">drawChar(x, y, c, color, bg, size)</code> : Draw a character on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of x-axis    
&emsp;&emsp;&emsp;`c` : A character to be drawn    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`bg` : The background of a character. Background size is 6 * 8 * textsize    
&emsp;&emsp;&emsp;`size` : Pixel size of charactor strock. Default is 1   

&emsp;<code class="code_accent">drawBitmap(x, y, bitmap, w, h, color)</code> : Draw a bitmap data on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : Start point of x-axis    
&emsp;&emsp;&emsp;`y` : Start point of y-axis    
&emsp;&emsp;&emsp;`bitmap` : A two dimensional array which consist of 0 and 1, 0 is black and 1 is white    
&emsp;&emsp;&emsp;`w` : Width of bitmap data    
&emsp;&emsp;&emsp;`h` : Height of bitmap data    
&emsp;&emsp;&emsp;`color` : The color of a character. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">setCursor(x, y)</code> : Set the cursor on OLED, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis point of cursor    
&emsp;&emsp;&emsp;`y` : y-axis point of cursor 

&emsp;<code class="code_accent">setTextSize(s)</code> : Set text size, This value is used in write()    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`s` : Pixel size of charactor strock. Default is 1 

&emsp;<code class="code_accent">setTextColor(c)</code> : Set text color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)   

&emsp;<code class="code_accent">setTextColorWithBg(c, b)</code> : Set text color and background color, This value is used in write()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : Text color value. BLACK(0) or WHITE(1)    
&emsp;&emsp;&emsp;`b` : Background color value. BLACK(0) or WHITE(1) 

&emsp;<code class="code_accent">drawPixel(x, y, color)</code> : Draw a dot on OLED    
&emsp;&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : The point of a dot    
&emsp;&emsp;&emsp;`y` : The point of a dot    
&emsp;&emsp;&emsp;`color` : The color of a dot    

&emsp;<code class="code_accent">setBrightness(Brightness)</code> : Set brightness of OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`Brightness` : Brightness value to be set   

&emsp;<code class="code_accent">invertDisplay(i)</code> : Change display mode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`i` : If i is `True`, dispaly mode is Inverse mode but if i is False, display mode is Normal mode. In Inverse mode, 0 is white and 1 is black    

&emsp;<code class="code_accent">istartscrollright(start, stop)</code> <br>&emsp;: Scroll the screen in the row-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling   

&emsp;<code class="code_accent">startscrollleft(start, stop)</code> <br>&emsp;: Scroll the screen in the row-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">startscrolldiagright(start, stop)</code> <br>&emsp;: Scroll the screen in the column-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">startscrolldiagleft(start, stop)</code> <br>&emsp;: Scroll the screen in the column-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`start` : Start point of scrolling    
&emsp;&emsp;&emsp;`stop` : Stop point of scrolling  

&emsp;<code class="code_accent">stopscroll()</code> : Stop scrolling the screen    

&emsp;<code class="code_accent">write(c)</code> : Write the character at location of cursor on OLED    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`c` : The character to be written   

&emsp;<code class="code_accent">setAutomode(automode)</code> : set automode    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    

<hr/>

## <span class="title">Class</span> <span class="title_accent">**Gesture**</span>    
<blockquote class="desc">Apds9960 Controlled via I2C Interface</blockquote>    

<h5>&emsp;Initialization</h5>   

&emsp;<code class="code_accent">Gesture(addr=APDS9960_ADDR)</code> : Gesture object inheriting from I2C Class (I2c Slave Address -> 0x39)    
	
<h5>&emsp;Methods</h5>   

&emsp;<code class="code_accent">isAvailable()</code> : return Gesture detection status(1). Wait until Gesture is detected    
&emsp;<code class="code_accent">read()</code> : return number as Gesture status.  
&emsp;&emsp;**Return**    
&emsp;&emsp;&emsp;`0` : "None" , `1` : "Left", `2` : "Right", `3` : "Up", `4` : "Down", `5`: "Near", `6` : "Far"    

&emsp;<code class="code_accent">readStr()</code> : return String as Gesture status.    
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

## <span class="title">Class</span> <span class="title_accent">**PixelDisplay**</span>    
<blockquote class="desc">Pixel Display controlled via Hardware PWM</blockquote>  
  
<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">PixelDisplay(width=8, height=8, gpio=-1, type=GRB, dma=10, automode=True, debug=False)</code> <br>&emsp;: PixelDisplay object    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`width` : Number of Pixel width    
&emsp;&emsp;&emsp;`height` : Number of Pixel height    
&emsp;&emsp;&emsp;`automode` : automode setting. `True` or `False`    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">display()</code> : send command from buffer. when Automode `False` use    
&emsp;<code class="code_accent">getRGBType()</code>: getRGBType    
&emsp;<code class="code_accent">RGBtoHEX(color_arr)</code> : convert RGB list data to HEX  
&emsp;<code class="code_accent">clear()</code> : clear PixelDisplay  
&emsp;<code class="code_accent">rainbow()</code> : display rainbow color on Pixel Display  
&emsp;<code class="code_accent">fill(color_arr)</code> : Fill PixelDisplay to one color    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color_arr` : A color to be filled. Type is list of [R, G, B]  
   
&emsp;<code class="code_accent">setColor(x, y, color_arr)</code> : set PixelDisplay color_arr on x,y    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis    
&emsp;&emsp;&emsp;`color_arr` : A color to be set. Type is list of [R, G, B] or HEX (0xRRGGBB)    

&emsp;<code class="code_accent">getColor(x, y)</code> : return color on x,y as INT type    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x-axis    
&emsp;&emsp;&emsp;`y` : y-axis 

&emsp;<code class="code_accent">setAutomode(automode)</code> : set automode. default `True`. if `False` set, shuld use display()    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`automode` : `True` or `False`    
   
&emsp;<code class="code_accent">setBrightness(brightness)</code> : set Brightness    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`brightness` : brightness (0~255)    
  
&emsp;<code class="code_accent">setColorInvert(invert)</code> : inver color. default `False`    
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`invert`  
&emsp;&emsp;&emsp;&emsp;`True` : input (255,0,0) -> (0,255,255)    
&emsp;&emsp;&emsp;&emsp;`False` : input (255,0,0) -> (255,0,0)    

---

## <span class="title">Class</span> <span class="title_accent">**TextLcd**</span>    
<blockquote class="desc">TextLcd</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">TextLcd()</code> <br>&emsp;: TextLcd object 

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">clear()</code> : Clear Textlcd. It make Textlcd became empty.  
&emsp;<code class="code_accent">returnHome()</code> : Move cursor to (0, 0).  
&emsp;<code class="code_accent">displayOn()</code> : Turn on the display. The display is turned on at first.  
&emsp;<code class="code_accent">displayOff()</code> : Turn off the display. Turned off display is not working.  
&emsp;<code class="code_accent">displayShiftR()</code> : Shift the display to right.  
&emsp;<code class="code_accent">displayShiftL()</code> : Shift the display to left.  
&emsp;<code class="code_accent">cursorShiftR()</code> : Shift cursor to right.  
&emsp;<code class="code_accent">cursorShiftL()</code> : Shift cursor to left.  
&emsp;<code class="code_accent">entryModeSet()</code> : Set Entry Mode.  
&emsp;<code class="code_accent">cursorOff()</code> : Turn off cursor.  
&emsp;<code class="code_accent">cursorOn(blink)</code> : Turn on cursor.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blink` : If True, cursor is blinking. Else False, cursor is always on. Default is False    

&emsp;<code class="code_accent">command(command)</code> : Send the command to TextLcd<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`command` : Command that to be sent to Textlcd.    

&emsp;<code class="code_accent">setCursor(x, y)</code> : Move cursor to (x, y). Unit is 1 block.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`x` : x axis of cursor. (0 ~ Width)    
&emsp;&emsp;&emsp;`y` : y axis of cursor. (0 ~ Height)    

&emsp;<code class="code_accent">data(data)</code> : Print 1byte data on the TextLcd. Data is written on the Textlcd.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`data` : Data to be sent to the Textlcd.    

&emsp;<code class="code_accent">print(string)</code> : Print string data on the Textlcd.<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`string` : String data to be sent to the Textlcd.    

---

## <span class="title">Class</span> <span class="title_accent">**Mpu6050**</span>    
<blockquote class="desc">Mpu6050</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Mpu6050(addr=MPU6050_ADDR)</code> <br>&emsp;: Mpu6050 object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`addr` : I2c slave address. Default is MPU6050_ADDR (0x68).    

&emsp;**Definitions**    
&emsp;<code class="code_accent">MPU6050_ADDR</code> : Mpu6050 I2C slave address. Value is 0x68   

&emsp;**Variables**    
&emsp;<code class="code_accent">accelRawX</code> : Raw accel data of X axis.    
&emsp;<code class="code_accent">accelRawY</code> : Raw accel data of Y axis.    
&emsp;<code class="code_accent">accelRawZ</code> : Raw accel data of Z axis.    
&emsp;<code class="code_accent">accelScaledX</code> : Scaled accel data of X axis.    
&emsp;<code class="code_accent">accelScaledY</code> : Scaled accel data of Y axis.    
&emsp;<code class="code_accent">accelScaledZ</code> : Scaled accel data of Z axis.    
&emsp;<code class="code_accent">gyroRawX</code> : Raw gyro data of X axis.    
&emsp;<code class="code_accent">gyroRawY</code> : Raw gyro data of Y axis.    
&emsp;<code class="code_accent">gyroRawZ</code> : Raw gyro data of Z axis.    
&emsp;<code class="code_accent">gyroScaledX</code> : Scaled gyro data of X axis.    
&emsp;<code class="code_accent">gyroScaledY</code> : Scaled gyro data of Y axis.    
&emsp;<code class="code_accent">gyroScaledZ</code> : Scaled gyro data of Z axis.    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">readAccel()</code> : Update accel variables.  
&emsp;<code class="code_accent">readGyro()</code> : Update gyro variables.  

---

## <span class="title">Class</span> <span class="title_accent">**Touch**</span>    
<blockquote class="desc">Touch</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Touch()</code> <br>&emsp;: Touch object 

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">read()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**Dust**</span>    
<blockquote class="desc">Dust</blockquote> 

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Dust()</code> <br>&emsp;: Dust object 

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">read()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**PwmController**</span>    
<blockquote class="desc">PwmController</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">PwmController()</code> <br>&emsp;: PwmController object 

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">setChannel(channel)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`channel` : ...    

&emsp;<code class="code_accent">setDuty(percent)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`percent` : ...    

&emsp;<code class="code_accent">setFreq(freq)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`freq` : ...    

&emsp;<code class="code_accent">setInvertPulse()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**RGBLed**</span>    
<blockquote class="desc">RGBLed</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">RGBLed(*ns)</code> <br>&emsp;: RGBLed object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*ns` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">on(color)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color` : ...    

&emsp;<code class="code_accent">off(color)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`color` : ...    

&emsp;<code class="code_accent">set(*colors)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*colors` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**ShiftRegister**</span>    
<blockquote class="desc">ShiftRegister</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">ShiftRegister(*ns)</code> <br>&emsp;: ShiftRegister object <br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*ns` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">shiftout(val)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ...    

&emsp;<code class="code_accent">fnd(val)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`val` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**StepMotor**</span>    
<blockquote class="desc">StepMotor</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">StepMotor(*ns)</code> <br>&emsp;: StepMotor object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`*ns` : ...    

<h5>&emsp;Definitions</h5>

&emsp;<code class="code_accent">SPEED_1</code> : ...    
&emsp;<code class="code_accent">SPEED_2</code> : ...    
&emsp;<code class="code_accent">SPEED_3</code> : ...    
&emsp;<code class="code_accent">ONE_PHASE_FULLSTEP</code> : ...    
&emsp;<code class="code_accent">TWO_PHASE_FULLSTEP</code> : ...    
&emsp;<code class="code_accent">HALFSTEP</code> : ...    
&emsp;<code class="code_accent">SPEED_SEQ</code> : ...    
&emsp;<code class="code_accent">ONE_PHASE_FULLSTEP_SEQ</code> : ...    
&emsp;<code class="code_accent">TWO_PHASE_FULLSTEP_SEQ</code> : ...    
&emsp;<code class="code_accent">HALFSTEP_SEQ</code> : ...    


<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">forward()</code> : ...  
&emsp;<code class="code_accent">backward()</code> : ...  
&emsp;<code class="code_accent">stop()</code> : ...  
&emsp;<code class="code_accent">setMode(mode)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`mode` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**Audio**</span>    
<blockquote class="desc">Audio</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Audio(blocking=True, cont=False)</code> <br>&emsp;: Audio object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blocking` : ...    
&emsp;&emsp;&emsp;`cont` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">stop()</code> : ...  
&emsp;<code class="code_accent">close()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**AudioPlay**</span>    
<blockquote class="desc">AudioPlay</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioPlay()</code> <br>&emsp;: AudioPlay object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blocking` : ...    
&emsp;&emsp;&emsp;`cont` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">run()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**AudioPlayList**</span>    
<blockquote class="desc">AudioPlayList</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioPlayList(blocking=True, cont=False)</code> <br>&emsp;: AudioPlayList object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`blocking` : ...    
&emsp;&emsp;&emsp;`cont` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">run()</code> : ...  
&emsp;<code class="code_accent">isPlay()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**AudioRecord**</span>    
<blockquote class="desc">AudioRecord</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">AudioRecord(file, sFormat=8, sChannel=1, sRate=48000, sFramePerBuffer=1024)</code> <br>&emsp;: AudioRecord object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`file` : ...    
&emsp;&emsp;&emsp;`sFormat` : ...    
&emsp;&emsp;&emsp;`sChannel` : ...    
&emsp;&emsp;&emsp;`sRate` : ...    
&emsp;&emsp;&emsp;`sFramePerBuffer` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">run()</code> : ...  

---

## <span class="title">Class</span> <span class="title_accent">**Tone**</span>    
<blockquote class="desc">Tone</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">Tone(tempo=100, volume=.5, rate=48000, channels=1)</code> <br>&emsp;: Tone object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`tempo` : ...    
&emsp;&emsp;&emsp;`volume` : ...    
&emsp;&emsp;&emsp;`rate` : ...    
&emsp;&emsp;&emsp;`channels` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">close()</code> : ...  
&emsp;<code class="code_accent">setTempo(tempo)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`tempo` : ...    

&emsp;<code class="code_accent">rest(duration)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`duration` : ...    

&emsp;<code class="code_accent">play(octave, pitch, duration)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`octave` : ...    
&emsp;&emsp;&emsp;`pitch` : ...    
&emsp;&emsp;&emsp;`duration` : ...    

---

## <span class="title">Class</span> <span class="title_accent">**SoundMeter**</span>    
<blockquote class="desc">SoundMeter</blockquote>

<h5>&emsp;Initialization</h5> 

&emsp;<code class="code_accent">SoundMeter(sampleFormat=pyaudio.paInt16, channelNums=1, framesPerBuffer=1024, sampleRate=48000)</code> <br>&emsp;: SoundMeter object<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`sampleFormat` : ...    
&emsp;&emsp;&emsp;`channelNums` : ...    
&emsp;&emsp;&emsp;`framesPerBuffer` : ...    
&emsp;&emsp;&emsp;`sampleRate` : ...    

<h5>&emsp;Methods</h5>  

&emsp;<code class="code_accent">stop()</code> : ...  
&emsp;<code class="code_accent">setCallback(func, *args)</code> : ...<br>
&emsp;&emsp;**Params**   
&emsp;&emsp;&emsp;`func` : ...    
&emsp;&emsp;&emsp;`*args` : ...    
