# HOME-AUTOMATION-WITH-BLUETOOTH-SERIAL-MONITOR-
String command;

int led = 8;
int bulb = 9;

void setup() {
  Serial.begin(9600);

  pinMode(led, OUTPUT);
  pinMode(bulb, OUTPUT);

  digitalWrite(led, LOW);
  digitalWrite( bulb, LOW);

  Serial.println("Bluetooth Simulation Ready (Use Serial Monitor)");
  Serial.println("1=led ON, 2=led OFF, 3= bulb ON, 4=bulb OFF");
}

void loop() {

  if (Serial.available()) {

    command = Serial.readStringUntil('\n');
    command.trim();

    if (command == "1") {
      digitalWrite(led, HIGH);
      Serial.println("led ON");
    }

    else if (command == "2") {
      digitalWrite(led, LOW);
      Serial.println("led OFF");
    }

    else if (command == "3") {
      digitalWrite(bulb, HIGH);
      Serial.println("bulb ON");
    }

    else if (command == "4") {
      digitalWrite(bulb, LOW);
      Serial.println("bulb OFF");
    }

    else {
      Serial.println("Invalid Command");
    }
  }
}
