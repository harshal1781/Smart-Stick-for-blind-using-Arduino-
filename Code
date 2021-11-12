// C++ code
//Smart Stick for blind
int triggerPin=6;
int echoPin=5;
int motorPin=4;
int vibPin=3;
int alarmPin=2;
int time, distance;
void setup()
{
  Serial.begin(9600);
  pinMode(triggerPin,OUTPUT);
  pinMode(echoPin,INPUT);
  pinMode(motorPin,OUTPUT);
  pinMode(vibPin,OUTPUT);
  pinMode(alarmPin,OUTPUT);
}

void loop()
{
  digitalWrite(triggerPin,HIGH);
  delayMicroseconds(10); 
  digitalWrite(triggerPin,LOW);
  time=pulseIn(echoPin,HIGH);
  distance=(time*0.034)/2;
  
  if(distance>=0 && distance<=35)
  {
    Serial.println (" Object is too near!!! ");
    Serial.print (" Distance= ");              
    Serial.println (distance); 
    digitalWrite(alarmPin,HIGH);
    digitalWrite(vibPin,HIGH);
    digitalWrite(motorPin,HIGH);
   
  }
  else if(distance>=36 && distance<=70)
  {
    Serial.println (" Object is  near!!! ");
    Serial.print (" Distance= ");              
    Serial.println (distance);  
    digitalWrite(alarmPin,HIGH);
    digitalWrite(vibPin,LOW);
    digitalWrite(motorPin,LOW);
  
  }
  else if(distance>70)
  {
    Serial.println (" object is far ");
    Serial.print (" Distance= ");              
    Serial.println (distance);        
    digitalWrite(alarmPin,LOW);
    digitalWrite(vibPin,LOW);
    digitalWrite(motorPin,LOW);
  
  }
  delay(500);
}
