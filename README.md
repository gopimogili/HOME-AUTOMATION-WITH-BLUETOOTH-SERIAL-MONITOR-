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

#Output

<img width="1866" height="872" alt="Image" src="https://github.com/user-attachments/assets/6c451a8e-c143-4318-892b-d798de319baf" />
<img width="1887" height="866" alt="Image" src="https://github.com/user-attachments/assets/2aa637b9-42ea-4f6c-ba2c-e9d0873a891a" />
<img width="1898" height="880" alt="Image" src="https://github.com/user-attachments/assets/7fa349ef-3d97-4c7a-b8fb-e8384cdbe4d0" />
<img width="1887" height="887" alt="Image" src="https://github.com/user-attachments/assets/252bbb11-500a-4202-ac29-34a727fa0580" />
