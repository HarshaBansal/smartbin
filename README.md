#smartbin
int trigpin=12;
int echopin=11;
int buzzer=4;
int sound=250;
long duration,cm;



void setup()
{
  Serial.begin(9600);
pinMode(trigpin,OUTPUT);
pinMode(echopin,INPUT);
pinMode(buzzer,OUTPUT);

}

void loop()
{
 digitalWrite(trigpin,LOW);
 digitalWrite(trigpin,HIGH);
 delayMicroseconds(10);
 digitalWrite(trigpin,LOW);
 pinMode(echopin,INPUT);
 duration=pulseIn(echopin,HIGH);
 cm=(duration/2)/29.1;
 
 if(cm<=40 || cm <=30){
 Serial.println("beep");
 digitalWrite(buzzer,HIGH);
 sound=250;

}
else
{
  
 Serial.print(cm);
 Serial.print("cm");
 Serial.println();
}
 delay(250);

}
	
	
	
