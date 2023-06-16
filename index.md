# Project Name Here
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Anvika V | Princeton Day School | Computer Engineering | Incoming Senior |

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone
For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Second Milestone
For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# First Milestone

![MilestoneOne](MilestoneOne.png)

For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project
This project started with developing simple a system that assists visually-impaired indaviduals in nagivating a space. It alerts the user of objects within a 70cm radius with either haptic or auditive feedback: a vibrating motor or buzzer. The circuit also has a 5mm red LED to make the 

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Schematics 
![Schematic1](Schematics1.png)

# Code
```c++
  const int pingTrigPin = 3; //Trigger connected to PIN 3
  const int pingEchoPin = 2; //Echo connected to PIN 2
  const int buz = 4; //Buzzer connected to PIN 4
  
  void setup() 
  {
    Serial.begin(9600);
    pinMode(buz, OUTPUT);
    pinMode(pingTrigPin, OUTPUT);
    pinMode(pingEchoPin, INPUT);
  }
  
  void loop()
  {
    long duration, cm; //Variables for wave duration and wave distance   
    digitalWrite(pingTrigPin, LOW); //Confirming that the trigPin is clear   
    delayMicroseconds(2);
    digitalWrite(pingTrigPin, HIGH); //Generating a wave by setting trigPin to HIGH for 5 minroseconds and then back to low
    delayMicroseconds(5);
    digitalWrite(pingTrigPin, LOW);
    duration = pulseIn(pingEchoPin, HIGH); //Storing the travel time is variable duration
    cm = microsecondsToCentimeters(duration); //Converting to distance   
    if(cm<=70 && cm>0) //Makes the light blink faster when the distance is smaller --> starts blinking at 70cm
    {
      int d= map(cm, 1, 100, 20, 2000); //d stores a variable that reformats a range
      digitalWrite(buz, HIGH); //Turning light on for .1 second  
      delay(100);
      digitalWrite(buz, LOW); //Turning light off 
      delay(d); //Waiting for a time that corresponds to the variable cm
    }
    Serial.print(cm);
    Serial.print("cm");
    Serial.println();
    delay(100);
  }
  
  long microsecondsToCentimeters(long microseconds)
  {
    return microseconds / 29 / 2;
  }
```

# Bill of Materials
| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Arduino Micro | Microcontroller | $24.90 | <a href="https://www.digikey.com/en/products/detail/arduino/A000053/4486332?s=N4IgTCBcDaIIwAYCsCC0iBsHUDsAmIAugL5A"> DigiKey </a> |
| Ultrasonic Sensor | Object Detection | $9 | <a href="https://www.amazon.com/Smraza-Ultrasonic-Distance-Mounting-Duemilanove/dp/B01JG09DCK/"> Amazon </a> |
| Vibrating Motor | Haptic Feedback | $11 | <a href="https://www.amazon.com/tatoko-vibration-Waterproof-8000-16000RPM-toothbrush/dp/B07KYLZC1S/"> Amazon </a> |
| Buzzer | Auditive Feedback | $7 | <a href="https://www.amazon.com/mxuteuk-Electronic-Computers-Printers-Components/dp/B07VK1GJ9X/"> Amazon </a> |
| 5mm Red LED | Visual Troubleshooting  | $6 | <a href="https://www.amazon.com/Diffused-Lighting-Electronics-Components-Emitting/dp/B01C3ZZT0A/"> Amazon </a> |
| Slide Switch | Selecting Haptic of Auditive Feedback  | $6 | <a href="https://www.amazon.com/HiLetgo-SS-12D00-Toggle-Switch-Vertical/dp/B07RTJDW27/"> Amazon </a> |
| 220Ω Resistor | Limiting Current to LED | $5.99 | <a href="https://www.amazon.com/MCIGICM-Values-Resistor-Assortment-Resistors/dp/B06WRQS97C/ref=asc_df_B06WRQS97C/?tag=hyprod-20&linkCode=df0&hvadid=312303208923&hvpos=&hvnetw=g&hvrand=2879797771863936635&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9003932&hvtargid=pla-586932991178&psc=1"> Amazon </a> |
| Breadboard | Intial Circuit Base | $9.99 | <a href="https://www.amazon.com/EL-CP-003-Breadboard-Solderless-Distribution-Connecting/dp/B01EV6LJ7G/ref=sr_1_11?keywords=solderless+breadboard&qid=1685564152&sr=8-11%20soldering%20kit11Amazonhttps://www.amazon.com/Soldering-Iron-Kit-Temperature-Desoldering/dp/B07S61WT16/ref=sxts_b2b_sx_reorder_acb_business"> Amazon </a> |
| Jumper Cables | Connecting Wires | $13.35 | <a href="https://www.amazon.com/QISF-Breadboard-Preformed-Anti-Static-Electronics/dp/B088WNZXFQ/ref=sr_1_6_sspa?crid=3BVYVZGBE5A3Z&keywords=boardboard+with+jumper+wires&qid=1686002634&sprefix=boardboard+with+jumper+wires%2Caps%2C83&sr=8-6-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFOWlRORjRCRUVHQTcmZW5jcnlwdGVkSWQ9QTA5Mjc5NjkxUktLUFAyVVJYRVBGJmVuY3J5cHRlZEFkSWQ9QTA5ODUyMjIyQ0IwTDM3VzIwQkFKJndpZGdldE5hbWU9c3BfbXRmJmFjdGlvbj1jbGlja1JlZGlyZWN0JmRvTm90TG9nQ2xpY2s9dHJ1ZQ=="> Amazon </a> |


# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
