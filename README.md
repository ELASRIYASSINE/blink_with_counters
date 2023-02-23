byte compteur1; 
byte compteur2;
int boutton1;
int boutton2;
void setup() {
  Serial.begin(9600);
  pinMode(2, INPUT_PULLUP);
  pinMode(4, INPUT_PULLUP);
  pinMode(13, OUTPUT);  
  pinMode(10, OUTPUT);
  }
void loop() {
  boutton1 = digitalRead(4);
  boutton2 = digitalRead(2);
  if ((boutton1 == LOW) && (compteur1<3))  {
digitalWrite(10, HIGH); //allume la LED
delay(500);
digitalWrite(10, LOW); //allume la LED
delay(500);
compteur1=compteur1+1; 
Serial.println("The button is pressed");
}
else if(boutton1 == HIGH) {
  compteur1=0;
  }
 if ((boutton2 == LOW) && (compteur2<5)) {
digitalWrite(13, HIGH); //allume la LED
delay(500);
digitalWrite(13, LOW); //allume la LED
delay(500);
compteur2=compteur2+1; 
Serial.println("The button is pressed");
}
else if(boutton2 == HIGH) {
  compteur2=0;
  }
}
