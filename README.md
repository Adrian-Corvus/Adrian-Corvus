char stringToMorseCode[] = "";

int audio8 = 8;
int note = 1200;

int dotLen = 100;
int dashLen = dotLen * 3;

void setup() {  
  Serial.begin(9600);              
}

void loop()
{ 
  char inChar = 0;          
  char inData[100] = "";
  String variable = "";
  String variable1 = "";
  int index1 = 0;
 
  if ( Serial.available() > 0 ) 
  {
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
  }
  String  stringToMorseCode = String(variable);                          

  for (int i = 0; i < sizeof(stringToMorseCode) - 1; i++)
  {
  char tmpChar = stringToMorseCode[i];
  tmpChar = toLowerCase(tmpChar);
  GetChar(tmpChar);
  }
}

void MorseDot()
{
  tone(audio8, note, dotLen);
  delay(dotLen);
}

void MorseDash()
{
  tone(audio8, note, dashLen);
  delay(dashLen);
}

void GetChar(char tmpChar)
{
  switch (tmpChar) 
  {
    case 'a': 
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'b':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'c':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'd':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100); 
    break;
    case 'e':
    MorseDot();
    delay(100);
    break;
    case 'f':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'g':
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'h':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'i':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'j':
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'k':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'l':
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'm':
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'n':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'o':
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'p':
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 'q':
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'r':
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 's':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    case 't':
    MorseDash();
    delay(100);
    break;
    case 'u':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'v':
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'w':
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'x':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'y':
    MorseDash();
    delay(100);
    MorseDot();
    delay(100);
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);
    break;
    case 'z':
    MorseDash();
    delay(100);
    MorseDash();
    delay(100);   
    MorseDot();
    delay(100);
    MorseDot();
    delay(100);
    break;
    default:
       break;
  }
}
