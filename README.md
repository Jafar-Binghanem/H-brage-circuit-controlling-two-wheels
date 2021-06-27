# H-brage-circuit-controlling-two-wheels

# An-Arduino-circuit-controlling-5-Servo-motor  
**Task 1,2.** An Arduino circuit controlling 5 Servo-motor to rotate 90° and then back to 0° via slidebutton simulated in TinkerCad (circuit and code)    
  
   **A. The code**  

```ruby
// C++ code
//
void setup()
{
  pinMode(11, OUTPUT);
  pinMode(13, INPUT);
  pinMode(9, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(4, INPUT);
  pinMode(3, OUTPUT);

}

void loop()
{
  int potValue=analogRead(A0); // to read the potentmetr value
  int pwmEn=map(potValue,0,1023,0,255);
   analogWrite(11,pwmEn); // we send the pwm to the en pins
   analogWrite(6,pwmEn);  
   
  

    if (digitalRead(13)==HIGH)
    {  digitalWrite(5,1); 
       digitalWrite(8,1);
       digitalWrite(3,0);
       digitalWrite(9,0); } 
    else 
       {  digitalWrite(5,0);
          digitalWrite(8,0);
          digitalWrite(3,1);
          digitalWrite(9,1);  } 
  
  
  delay(100); // Wait for 1000 millisecond(s)
  }
  
  
 

 

  ```  
  
 **B. The circuit**  
 
 There is no H-brage L298, so Iused instead a L293. This IC has two sides, with each side controlling one single dc motor (wheel) independently of the other dc motor. For each side there are two inputs and two outputs. When one of the input is high and the other is (must be) low, the motor moves in a specific direction. if the values for inputs were reversed, that motor will move in the other direction. Power 1 must be supplied by 5V to perform the logic inside the IC. Pwer 2 is provide the voltage required by the dc motors. We also provide a pwm signal modified by the potentaimeter to pin 1 and pin 9 (each controls two outputs at one side -one dc motor-).     
   
   
 
 ![Circuit](Screenshot(228).png)
 
  **C. The simulation design**  
  
   [Click here to show the project in TinkerCad](https://www.tinkercad.com/things/4dxSFPiaqYW)     
     
       
     
