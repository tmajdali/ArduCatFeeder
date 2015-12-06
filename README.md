# ArduCatFeeder

#include <Servo.h>
Servo myservo1;
Servo myservo2;
Servo myservo3;
Servo myservo4;
Servo myservo5;
Servo myservo6;
Servo myservo7;
Servo myservo8;
const long oneSecond = 1000;  // a second is a thousand milliseconds
const long oneMinute = oneSecond * 60;
const long oneHour   = oneMinute * 60;
const long halfDay   = oneHour * 12;
const long oneDay    = oneHour * 24;
// min = 60000
// hour = 3600000
// 12 h = 43200000
// day = 86400000
// 2 days = 172800000
//3 days = 259200000
// 4 days = 345600000

void setup() {
  myservo1.attach (9) ;
    myservo2.attach (10) ;
  myservo3.attach (A0) ;
  myservo4.attach (A1) ;
    myservo5.attach (A2) ;
      myservo6.attach (A3) ;
        myservo7.attach (A4) ;
          myservo8.attach (A5) ;
          Serial.begin(9600);
  // put your setup code here, to run once:

}

void loop() {
  long timer = millis();

if ( timer > 0 && timer <10)
{
   myservo1.writeMicroseconds (500); // sec 1 o
   myservo2.writeMicroseconds (900) ; // sev 2 o
   myservo3.writeMicroseconds (2400) ; // sev 3 o
  myservo4.writeMicroseconds (2400) ; // sev 4 o
   myservo5.writeMicroseconds (1900) ; // sev 5 o 
  myservo6.writeMicroseconds (1700) ; // sev 6 o 
  myservo7.writeMicroseconds (1900) ; // sev 7 o
  myservo8.writeMicroseconds (2400) ; // sev 8 o
  delay(3000);
 //--------------------------------test o
 myservo1.writeMicroseconds (1200) ; // sev 1 c (500)
  myservo2.writeMicroseconds (2200) ; // sev 2 c (900)
  myservo3.writeMicroseconds (1500) ; // sev 3 c (2400)
  myservo4.writeMicroseconds (1500) ; // sev 4 c (2400)
  myservo5.writeMicroseconds (700) ; // sev 5 c (1900)
  myservo6.writeMicroseconds (500) ; // sev 6 c (1700)
  myservo7.writeMicroseconds (700) ; // sev 7 c (1900)
  myservo8.writeMicroseconds (1500) ; // sev 8 c (2400)
  delay(3000);
}
 //-----------------------------------------------------
 if( timer >= 86400000)
  //delay(halfDay);
{
 myservo1.writeMicroseconds (500); // sec 1 o
  myservo2.writeMicroseconds (900) ; // sev 2 o
}
   //delay(oneDay);
   //---------------- hole 1
   if ( timer >= 172800000 )
   {
  myservo3.writeMicroseconds (2400) ; // sev 3 o
  myservo4.writeMicroseconds (2400) ; // sev 4 o
   }
 // delay(oneDay);
   //---------------- hole 2
   if ( timer >= 259200000 )
   {
  myservo5.writeMicroseconds (1900) ; // sev 5 o 
 myservo6.writeMicroseconds (1700) ; // sev 6 o 
   }
  //delay(oneDay);
   //---------------- hole 3
   if ( timer >= 345600000 )
   {
   myservo7.writeMicroseconds (1900) ; // sev 7 o
  myservo8.writeMicroseconds (2400) ; // sev 8 o
   }
 // delay(2000);
 //---------------- hole 4
}
