const int ledPin = 8;       
const int sensorPin = A0;   
int sensorValue;            
const int threshold = 500;  

void setup() {
    pinMode(ledPin, OUTPUT);    
    Serial.begin(9600);         
}

void loop() {
    sensorValue = analogRead(sensorPin);   
    Serial.print("Light value : ");
    Serial.println(sensorValue);           

    if(sensorValue < threshold){
        Serial.println("dark");           
        digitalWrite(ledPin, HIGH);       
    } else {
        Serial.println("light");          
        digitalWrite(ledPin, LOW);        
    }

    delay(500); 
}
