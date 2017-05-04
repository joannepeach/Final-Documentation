# Final-Documentation
![200w_d](https://cloud.githubusercontent.com/assets/25276044/25725959/e324fa62-30d6-11e7-911d-f9adc68008c6.gif)
 In the beginning, I got a microphone that detects sound called Max 1904. Then, I checked the functionality of it by going on Adafruit and found a code that measured sound levels.
 
 const int sampleWindow = 50; // Sample window width in mS (50 mS = 20Hz)
unsigned int sample;
 
void setup() 
{
   Serial.begin(9600);
}
 
 
void loop() 
{
   unsigned long startMillis= millis();  // Start of sample window
   unsigned int peakToPeak = 0;   // peak-to-peak level
 
   unsigned int signalMax = 1024;
   unsigned int signalMin = 50;
 
   // collect data for 50 mS
   while (millis() - startMillis < sampleWindow)
   {
      sample = analogRead(A0);
      if (sample < 1024)  // toss out spurious readings
      {
         if (sample > signalMax)
         {
            signalMax = sample;  // save just the max levels
         }
         else if (sample < signalMin)
         {
            signalMin = sample;  // save just the min levels
         }
      }
   }
   peakToPeak = signalMax - signalMin;  // max - min = peak-peak amplitude
   double volts = (peakToPeak * 100) / 1024;  // convert to volts
 
   Serial.println(sample);
}
## What I did
Then, I adjusted volts to PeaktoPeak to measure the loudest sound it can detect and adjusted accordingly. I plugged in an LED light and resistors on the breadboard that connected to the Arduino. By adding multiple LED lights, I learned  you can called each pin to light up at different light levels. This helped me understand the sensitivity of the microphone. After, I replaced the LED lights by purchasing an neopixel that has multiple lights attached so I can work with activating certain lights. This was in pursuit to create a device that reacted to the sounds of two people arguing. 
![img_8973](https://cloud.githubusercontent.com/assets/25276044/25725727/240c008a-30d6-11e7-98ab-2bffa94d8046.JPG)
![img_8974 2](https://cloud.githubusercontent.com/assets/25276044/25725737/29a59e16-30d6-11e7-9e97-fae9c73315c3.JPG)


## How I did it
I seeked guidance from Caroline and J.D.'s help along with looking at other people on Adafruit use neopixels. 
I learned that when one finds a code online, there's alot of unecessary code that can be simplified so that I can have a better control of it. 
The physical construction of wiring the neopixel required sautering and careful attention towards using heat shrink wraps to make the cohesion cleaner. Using my laptop as the energy source, i was able to fidget around with the code and figure out how to make the lights change in a gradient. 

## What I Learned Along the Way
My biggest take away from this project was being able to deal with large amonunts of code. Although it felt like I learned the basic parts of programming, i was proud of be able to unravel the meaning of the code. Also, I was able to familiarize myself with different materials and learning that some microphones were simplier to use. Therefore, I was able to use the simplest materials for my project. 

## How I Would do Differently
 What I would do differently is I would create some sort of reactant towards when two people are not talking. Although it is unhealthy to be yelling at someone, It is also unhealthy to not be able to communicate thoughts. Thus, I would add a feature that encourages talking. 
 Also, I would dig deeper into the code and adjust the sensitivity of the microphone. 

## Most Difficult Problems
The most difficult problem was figuring out which microphones and which resistors were necessary to be compatible with the Arduino. I overcame that problem by trying multiple parts out and bothering countless hybrid lab monitors. 
Another difficult problem was sautering the neopixel because the part was so small that it difficult to keep a steady hand. Also, I researched on Sparkfun and Adafruit past projects that people have done to guide the process in which I code my project. 
However, that led me to another problem cause I found a code that required me to attach the microphone onto a battery but that was not necessary because it was a code that required amplifying sound. I learned I was looking for a sound measurer. A final problem I dealt with was using a microphone "Max 9814" which had parts what were not needed and made my code confusing. So I switched to microphone outbreak reader which made my life easier. 
Lastly, I order the neopixel on Adafruit and it was taking quite a while coming. Thus, I had to use LED's as substitutes. When the neopixel came in, it was the night before the project was due. Figuring out how to activate the neopixel was a struggle and then connecting it to the microphone helped me understand how each part functioned.

Helpful Links: https://learn.adafruit.com/3d-printed-led-microphone-flag/overview
https://www.adafruit.com/product/1713
https://learn.adafruit.com/adafruit-microphone-amplifier-breakout/measuring-sound-levels
https://www.adafruit.com/product/1463


