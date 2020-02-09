//Sound according to every character

void loop()
{
  char inChar = 0;         
  char inData[100] = "";
  String variable = "";
  String variable1 = "";
  int index1 = 0;

  if ( Serial.available() > 0 ) {                     
   while (Serial.available() > 0 && index1 < 100)
    {
      delay(100);
      inChar = Serial.read();
      inData[index1] = inChar;
      index1++;
      inData[index1] = '\0';
    }
    variable.toUpperCase();
    for (byte  i = 0 ; i < 100 ; i++) {
      variable.concat(String(inData[i]));  
    }
    delay(20);
