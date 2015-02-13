# Sketch_BlinkRed_SolidGreen

#define LED 13     // the pin for the LED
#define BUTTON  7
#define LED2 12// the input pin where the
                    // pushbutton is connected
                    
int val = 0;        // val will be used to store the state
                   // of the input pin
                   
int old_val = 0;    // this variable stores the previous
                    // value of "val"
                    
int state = 0;      // 0 = LED off and 1 = LED on

void setup() {
pinMode(LED, OUTPUT);     // tell Arduino LED is an output
pinMode(BUTTON, INPUT);
pinMode(LED2, OUTPUT);// and BUTTON is an input
}

void loop(){
val = digitalRead(BUTTON);   // read input value and store it
                             
if ((val == HIGH) && (old_val == LOW)){
state = 1 - state;
delay(500);
}

old_val = val;             // val is now old, let's store it

if (state == 1) {
digitalWrite(LED, HIGH);      // turn LED ON
} else {
digitalWrite(LED, LOW);
digitalWrite(LED2, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(200);              // wait for a second
  digitalWrite(LED2, LOW);    // turn the LED off by making the voltage LOW
  delay(100); 

}

}
