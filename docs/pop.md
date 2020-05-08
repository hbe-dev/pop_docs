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

<br>

&emsp; **Object Initialize**

&emsp; `Out(n)` : Out Object  

&emsp; Params    
&emsp; &emsp;  n : GPIO Number Connected to the Output Device

&emsp; **Methods**

&emsp; `on()`
		: Set GPIO Connected to Output Device to HIGH    

&emsp; `off()` 
		: Set GPIO Connected to Output Device to LOW   

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Led**    
> LEDs are controlled via GPIO    

* Object Initialize    
	* Led(n) : Led Object inheriting from Out Class    
		* Params    
			n : GPIO Number Connected to the LED    
## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Leds**    
> LEDs are controlled via GPIO    

* Object Initialize    
	* Leds(n) : Leds Object inheriting from Led Class    
		* Params    
			n : list Number defined board config Connected to the LED    
* Methods    
	* allOn()    
		: Set all GPIO Connected to Output Device to HIGH    
	* allOff()    
		: Set all GPIO Connected to Output Device to LOW    

<hr/> 

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Input**    
> Read the Input Device through GPIO    

* Object Initialize    
	* Input(n,activeHigh=Ture) : Input Object    
		* Params    
			n : GPIO Number Connected to the Input Device    
			activeHigh : Used to check if the Input Device is HIGH when pressed , Default True    

* Defines    
	* FALLING : Detect Falling Edge    
	* RISING : Detect Rising Edge    
	* BOTH : Detect Both Side    

* Methods    
	* read() : Read the Input Device Status    
	* setCallback(func,param=None,type=BOTH) : Set Callback Function When Detect Edge    
		* Params    
			func : Function to use when calling Callback    
			param : Arguments passed to the Callback function , Default None    
			type : Call condition of Callback function , Default BOTH    

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Switch**    
> Read the switch status through GPIO    

* Object Initialize    
	* Switch(n) : Switch Object inheriting from Input Class    
		* Params    
			n : GPIO Number Connected to the Switch    

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Switches**    
> Read the switch status through GPIO    

* Object Initialize    
	* Switches(n) : Switch Object inheriting from Input Class    
		* Params    
			n : list Number defined board config Connected to the Switch    

<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **SpiAdc**    
> adc chip control through spi interface    

* Object Initialize    
	* SpiAdc(channel, device=0, bus=0, speed=1000000) : SpiAdc object    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)  
			
* Defines    
	* TYPE_AVERAGE : Average data based on sampling count    
	* TYPE_NORMAL : Unaveraged raw data    
	* MODE_FULL : Call Callback function always    
	* MODE_INCLUSIVE : If data is in arange(max, min), call Callback function    
	* MODE_EXCLUSIVE : If data is over arange, call Callback function    

* Methods    
	* setChipSelect(cs) : Set SPI Chip Select PIN    
		* Params    
			cs : Chipselect GPIO for SPI Interface    
	* setCallback(func,param=None,type=TYPE_AVERAGE,mode=MODE_FULL,min=0,max=ADC_MAX) : Set up callback function for automatic data read    
		* Params    
			func : Function to use when calling Callback    
			param : Arguments passed to the Callback function , Default None    
			type : Data Read Type , Default TYPE_AVERAGE    
			mode : Select Mode , Default MODE_FULL    
			min : analog data minimum , Default 0    
			max : analog data maximum , Default 4095 (MCP3208 12bit ADC Chip)    
	* setSample(sample) : Set Sampling Count    
		* Params    
			sample : Sampling count    
	* getSample() : Get Sampling Count    
	* read() : Read Data from Device (Raw Type)    
	* readAverage() : Read Average Data from Device    
	* readVolt(ref=3.3,max=3020.0) : Read Data from Device (Voltage Type)    
		* Params    
			ref : Reference Voltage    
			max : Maximum value of raw data    
	* readVoltAverage(ref=3.3,max=3020.0) : Read Data from Device (Voltage Type)    
		* Params    
			ref : Reference Voltage    
			max : Maximum value of raw data    
	* run() : Read data and call Callback function according to mode    
    
## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Psd**    
> Distance measurement using PSD sensor    

* Object Initialize    
	* Psd(channel=-1, device=0, bus=0, speed=1000000) : PSD object inheriting from SpiAdc Class    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)    

* Methods    
	* calcDist(val,calibration=1.1) : Calculate distance value from raw data    
		* Params    
			val : ADC Raw Data    
			calibration : Calibration Value, Default 1.1    
			
## <span style="font-size:0.6em; font-weight:normal;">Class</span> **CDS**  
> Light measurement using CDS sensor    

* Object Initialize    
	* Cds(channel=-1, device=0, bus=0, speed=1000000) : Cds object inheriting from SpiAdc Class    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
* Methods    
	* setCalibrationPseudoLx(func) : Set calibration function    
		* Params    
			func : Calibration function    
	* readAverage() : Read lux data from device and calibration function    

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Sound**    
> Ambient sound measurement using Sound sensor    

* Object Initialize    
	* Sound(channel=-1, device=0, bus=0, speed=1000000) : Sound object inheriting from SpiAdc Class    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Vr**    
> Voltage measurement with variable resistor    

* Object Initialize    
	* Vr(channel=-1, device=0, bus=0, speed=1000000) : Vr object inheriting from SpiAdc Class    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)    
			
## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Potentiometer**    
> Voltage measurement with variable resistor    

* Object Initialize    
	* Potentiometer(channel=-1, device=0, bus=0, speed=1000000) : Potentiometer object inheriting from SpiAdc Class    
		* Params    
			channel : ADC Channel    
			device : SPI Interface Channel , Default 0 (in Raspberry Pi)    
			bus : Not Used..    
			speed : SPI Interface Clock Speed , Default 1000000(1MHz)    

* Methods    
	* setRangeTable(table) : Set potentiometer range table    
		* Params    
			table : Table with 10 elements    
			ex. [48, 300, 700, 1090, 1540, 1945, 2320, 2715, 2980, 3040]    
	* getRangeTable() : return range table    
	* readAverage() : return level from range table    

<hr/>	

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **PiezoBuzzer**    
* Class Description  : PiezoBuzzer controlled via Software PWM    
* Object Initialize    
	* PiezoBuzzer(n) : PiezoBuzzer object inheriting from PopThread    
		* Params    
			n : GPIO Number Connected to the PiezoBuzzer defined board setting or Can setting manually    

* Methods    
	* setTempo(n) : Set tempo value    
		* Params    
			n : Value to be set to tempo    
	* getTempo() : Get tempo value    
	* tone(scale,pitch,duration) : Play a note on piezo buzzer during duration value    
		* Params    
			scale : Scale value to play on piezo buzzer (int type)    
			pitch : Pitch value to play on piezo buzzer. 'Do' is 1, 'Do♯' is 2, 'Re' is 3 and 'Si' is 12    
			duration : Tone is playing during duration value    
	* rest(duration) : Stop to play piezo buzzer    
		* Params    
			duration : The duration of the stopping    
	* play(sheet) : play music by sheet    
		* Params    
			sheet : list [[scale],[pitch],[duration]]    
	* isPlay() : return play status    

<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Oled**    
> Oled Controlled vi I2C Interface    

* Object Initialize    
	* Oled( addr=OLED_ADDR, type=OLED_NONE_TYPE, automode=True) : Oled object inheriting from I2C Class (I2c Slave Address -> 0x3c). This method calls init(), clearDisplay()    
		* Params    
			addr : OLED I2C ADDR.default 0x3c    
			type : OLED Type. difined board config    
			automode : select automode. default True    

* Defines    
	* OLED_SSD1306_I2C_128x32 : OLED device type number, if model name is 'SSD1306', select this type    
	* OLED_SH1106_I2C_128x64 : OLED device type number, if model name is 'SSH1106', select this type    
	* BLACK : In OLED, you can use only 2 colors. One of them is black. Numeric value is 0    
	* WHITE : Another of them is white. Numeric value is 1    

* Methods    
	* init(type=OLED_SH1106_I2C_128x64) : Initialize OLED and set width/height of OLED. This method calls setTextSize(), setTextColor(), clearDisplay()    
		* Params    
			type : Select OLED type    
	* print(string) : Print a string on OLED. Replace '\n' to New-Line    
		* Params    
			string: The string to print on OLED    
	* drawCircle(x0, y0, r, color) : Draw a circle on OLED    
		* Params    
			x0 : Start point of x-axis    
			y0 : Start point of y-axis    
			r : Radious of the circle    
			color : The color of a circle. BLACK(0) or WHITE(1)    
	* fillCircle(x0, y0, r, color) : Draw a filled circle on OLED    
		* Params    
			x0 : Start point of x-axis    
			y0 : Start point of y-axis    
			r : Radious of the circle    
			color : The color of a circle. BLACK(0) or WHITE(1)    
	* drawLine(x0, y0, x1, y1, color) : Draw a line on OLED    
		* Params    
			x0 : Start point of x-axis    
			y0 : Start point of y-axis    
			x1 : End point of x-axis    
			y1 : End point of y-axis    
			color : The color of a line. BLACK(0) or WHITE(1)    
	* drawRect(x, y, w, h, color) : Draw a rectangle on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Width of the rectangle    
			h : Height of the rectangle    
			color : The color of a rectangle. BLACK(0) or WHITE(1)    
	* fillRect(x, y, w, h, color) : Draw a filled rectangle on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Width of the rectangle    
			h : Height of the rectangle    
			color : The color of a rectangle. BLACK(0) or WHITE(1)    
	* drawVerticalBargraph(x, y, w, h, color, percent) : Draw a graph on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Width of the graph    
			h : Full height of the graph    
			color : The color of the graph. BLACK(0) or WHITE(1)    
			percent : The percentage of a graph. The direction of graph is always up-side    
	* drawHorizontalBargraph(x, y, w, h, color, percent) : Draw a graph on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Full width of the graph    
			h : Height of the graph    
			color : The color of the graph. BLACK(0) or WHITE(1)    
			percent : The percentage of a graph. The direction of graph is always right-side    
	* drawRoundRect(x, y, w, h, r, color) : Draw a rounded rectangle on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Width of the rounded rectangle    
			h : Height of the rounded rectangle    
			r : Curvature of edge of the rounded rectangle    
			color : The color of a graph. BLACK(0) or WHITE(1)    
	* fillRoundRect(x, y, w, h, r, color) : Draw a rounded and filled rectangle on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			w : Width of the rounded rectangle    
			h : Height of the rounded rectangle    
			r : Curvature of edge of the rounded rectangle    
			color : The color of a graph BLACK(0) or WHITE(1)    
	* drawTriangle(x0, y0, x1, y1, x2, y2, color) : Draw a triangle on OLED    
		* Params    
			x0 : First point of x-axis    
			y0 : First point of y-axis    
			x1 : Second point of x-axis    
			y1 : Second point of y-axis    
			x2 : Third point of x-axis    
			y2 : Third point of y-axis    
			color : The color of a triangle. BLACK(0) or WHITE(1)    
	* fillTriangle(x0, y0, x1, y1, x2, y2, color) : Draw a filled triangle on OLED    
		* Params    
			x0 : First point of x-axis    
			y0 : First point of y-axis    
			x1 : Second point of x-axis    
			y1 : Second point of y-axis    
			x2 : Third point of x-axis    
			y2 : Third point of y-axis    
			color : The color of a triangle. BLACK(0) or WHITE(1)    
	* drawChar(x, y, c, color, bg, size) : Draw a character on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of x-axis    
			c : A character to be drawn    
			color : The color of a character. BLACK(0) or WHITE(1)    
			bg : The background of a character. Background size is 6 * 8 * textsize    
			size : Pixel size of charactor strock. Default is 1    
	* drawBitmap(x, y, bitmap, w, h, color) : Draw a bitmap data on OLED    
		* Params    
			x : Start point of x-axis    
			y : Start point of y-axis    
			bitmap : A two dimensional array which consist of 0 and 1, 0 is black and 1 is white    
			w : Width of bitmap data    
			h : Height of bitmap data    
			color : The color of a character. BLACK(0) or WHITE(1)    
	* setCursor(x, y) : Set the cursor on OLED, This value is used in write()    
		* Params    
			x : x-axis point of cursor    
			y : y-axis point of cursor    
	* setTextSize(s) : Set text size, This value is used in write()    
		* Params    
			s : Pixel size of charactor strock. Default is 1    
	* setTextColor(c) : Set text color, This value is used in write()    
		* Params    
			c : Text color value. BLACK(0) or WHITE(1)    
	* setTextColorWithBg(c, b) : Set text color and background color, This value is used in write()    
		* Params    
			c : Text color value. BLACK(0) or WHITE(1)    
			b : Background color value. BLACK(0) or WHITE(1)    
	* width() : Retun widht of OLED    
	* height() : Return height of OLED    
	* drawPixel(x, y, color) : Draw a dot on OLED    
		* Params    
			x : The point of a dot    
			y : The point of a dot    
			color : The color of a dot    
	* setBrightness(Brightness) : Set brightness of OLED    
		* Params    
			Brightness : Brightness value to be set    
	* invertDisplay(i) : Change display mode    
		* Params    
			i : If i is True, dispaly mode is Inverse mode but if i is False, display mode is Normal mode. In Inverse mode, 0 is white and 1 is black    
	* istartscrollright(start, stop) : Scroll the screen in the row-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
		* Params    
			start : Start point of scrolling    
			stop : Stop point of scrolling    
	* startscrollleft(start, stop) : Scroll the screen in the row-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
		* Params    
			start : Start point of scrolling    
			stop : Stop point of scrolling    
	* startscrolldiagright(start, stop) : Scroll the screen in the column-right direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
		* Params    
			start : Start point of scrolling    
			stop : Stop point of scrolling    
	* startscrolldiagleft(start, stop) : Scroll the screen in the column-left direction, Scroll method isn't working in OLED_SH1106_I2C_128x64    
		* Params    
			start : Start point of scrolling    
			stop : Stop point of scrolling    
	* stopscroll() : Stop scrolling the screen    
	* display() : Display buffer data on OLED    
	* clearDisplay() : Clear the data on OLED    
	* write(c) : Write the character at location of cursor on OLED    
		* Params    
			c : The character to be written    
	* setAutomode(automode) : set automode    
		* Params    
			automode : True or False    

<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **Gesture**    

> Apds9960 Controlled via I2C Interface    

* Object Initialize    
	* Gesture(addr=APDS9960_ADDR) : Gesture object inheriting from I2C Class (I2c Slave Address -> 0x39)    
	
* Methods    
	* isAvailable() : return Gesture detection status(1). Wait until Gesture is detected    
	* read() : return number as Gesture status.    
		0 : "None" , 1 : "Left", 2 : "Right", 3 : "Up", 4 : "Down", 5: "Near", 6 : "Far"    
	* readStr() : return String as Gesture status.    
		"None" , "Left", "Right", "Up", "Down", "Near", "Far"    
		
* Inner class Light    
	* Light() : Light object    
	* Methods    
		* read() : return light value    
		
* Inner class Color    
	* Color() : Color object    
	* Methods    
		* readRed() : return Red value    
		* readGreen() : return Green value    
		* readBlue() : return Blue value    
* Inner class Proximity    
	* Proximity() : Proximity object    
	* Methods    
		* read() : return Proximity value    
	
<hr/>

## <span style="font-size:0.6em; font-weight:normal;">Class</span> **PixelDisplay**    
> Pixel Display controlled via Hardware PWM  
  
* PixelDisplay(width=8, height=8, gpio=-1, type=GRB, dma=10, automode=True, debug=False) : PixelDisplay object    
	* Params    
		width : Number of Pixel width    
		height : Number of Pixel height    
		automode : automode setting. True/False    

* Methods    
	* fill(color_arr) : Fill PixelDisplay to one color    
		* Params    
			color_arr : A color to be filled. Type is list of [R, G, B]    
	* clear() : clear PixelDisplay    
	* setColor(x, y, color_arr) : set PixelDisplay color_arr on x,y    
		* Params    
			x : x-axis    
			y : y-axis    
			color_arr : A color to be set. Type is list of [R, G, B] or HEX (0xRRGGBB)    
	* getColor(x, y) : return color on x,y as INT type    
		* Params    
			x : x-axis    
			y : y-axis    
	* setAutomode(automode) : set automode. default True. if False set, shuld use display()    
		* Params    
			automode : True or False    
	* rainbow() : display rainbow color on Pixel Display    
	* setBrightness(brightness) : set Brightness    
		* Params    
			brightness : brightness (0~255)    
	* display() : send command from buffer. when Automode False use    
	* getRGBType() : getRGBType    
	* RGBtoHEX(color_arr) : convert RGB list data to HEX    
	* setColorInvert(invert) : inver color. default False    
		* Params    
			invert = True : input (255,0,0) -> (0,255,255)    
			invert = False : input (255,0,0) -> (255,0,0)    

