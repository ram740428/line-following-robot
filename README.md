#define LS 2 // left sensor
#define RS 3 // right sensor

/*-------definning Outputs------*/
#define LM1 4 // left motor
#define LM2 5 // left motor
#define RM1 6 // right motor
#define RM2 7 // right motor

void setup()
{
pinMode(LS, INPUT);
pinMode(RS, INPUT);
pinMode(LM1, OUTPUT);
pinMode(LM2, OUTPUT);
pinMode(RM1, OUTPUT);
pinMode(RM2, OUTPUT);
}

void loop()
{
if(!(digitalRead(LS)) && !(digitalRead(RS))) // Move Forward (digitalRead(LS) && digitalRead(RS))
{
digitalWrite(LM1, LOW);
digitalWrite(LM2, HIGH);
digitalWrite(RM1, LOW);
digitalWrite(RM2, HIGH);
}

if(!(digitalRead(LS)) && digitalRead(RS)) // Turn right
{
digitalWrite(LM1, LOW);
digitalWrite(LM2, HIGH);
digitalWrite(RM1, LOW);
digitalWrite(RM2, LOW);
}

if(digitalRead(LS) && !(digitalRead(RS))) // turn left
{
digitalWrite(LM1, LOW);
digitalWrite(LM2, LOW);
digitalWrite(RM1, LOW);
digitalWrite(RM2, HIGH);
}

if(digitalRead(LS) && digitalRead(RS)) // stop !(digitalRead(LS)) && !(digitalRead(RS))
{
digitalWrite(LM1, LOW);
digitalWrite(LM2, LOW);
digitalWrite(RM1, LOW);
digitalWrite(RM2, LOW);
}
}
