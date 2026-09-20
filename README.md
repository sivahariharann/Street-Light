## Name: SIVAHARIHARAN J

## Register No: 212224223004

# Automatic Street Light Controller Using LDR

## Aim

To design and implement an automatic street light controller using an LDR sensor in hardware.

## Components Required

* General-purpose microcontroller/controller
* LDR sensor
* 10 kΩ resistor
* LED
* 220 Ω resistor
* Breadboard
* Jumper wires
* Power supply

## Circuit Connections
            
LDR output   -            A0

LED positive terminal  -    Digital Pin

LED negative terminal   -   GND through 220 Ω resistor

LDR      -                  5V and GND through voltage divider 

## Working

The LDR senses the intensity of the surrounding light.

When the surrounding light intensity decreases, the controller detects darkness through the LDR and switches the street light ON.

When sufficient light is available, the controller switches the street light OFF.

The controller continuously reads the LDR sensor value and compares it with a predefined threshold value to control the street light automatically.

## Procedure

Step1: Open the Arduino IDE
Step2: Go to file and select new file option
Step3: Select the required controller board
Step4: Type the program and select save option to save the program
Step5: Go to sketch and select verify or compile options
Step6: If no error Hex file will be generated in the temporary folder
Step7: Connect all the components as per the circuit diagram
Step8: Connect the programming cable with controller and PC.
Step9: Upload the program in the controller.
Step10:Verify that the LED turns ON.
Step11: Expose the LDR to light and verify that the LED turns OFF.

## Theory

* What is Light Dependent Resistor?
  
An electronic component like LDR or light-dependent resistor is responsive to light. 
Once light rays drop on it, then immediately the resistance will be changed. 
The resistance values of an LDR may change over several orders of magnitude. The resistance value will be dropped when the light level increases. 
The resistance values of LDR in darkness are several megaohms whereas in bright light it will be dropped to hundred ohms. So due to this change in resistance, these resistors are extremely used in different applications. 
The LDR sensitivity also changes through the incident light’s wavelength. The designing of LDRs can be done by using semiconductor materials to allow their light-sensitive properties. 
The famous material used in this resistor is CdS (cadmium sulfide), even though the utilization of this material is currently restricted in European countries due to some environmental issues while using this material. 
Likewise, CdSe (cadmium selenide) is also restricted and additional materials that can be employed mainly include PbS (lead sulfide), InS ( indium antimonide). Even though for these resistors, a semiconductor material is used, because they are simply passive devices and they do not have a PN-junction. 
This detaches them from other LDRs such as phototransistors & photodiodes.

<img width="400" height="250" alt="image" src="https://github.com/user-attachments/assets/81514f16-e0ac-41a2-aaad-52d5e0e3f5a4" />

* Working Principle of Light Dependent Resistor
  
The working principle of an LDR is photoconductivity, which is nothing but an optical phenomenon. 
When the light is absorbed by the material then the conductivity of the material enhances. 
When the light falls on the LDR, then the electrons in the valence band of the material are eager to the conduction band. 
But, the photons in the incident light must have energy superior to the bandgap of the material to make the electrons jump from one band to another band (valance to conduction). 
Hence, when light having ample energy, more electrons are excited to the conduction band which grades in a large number of charge carriers. 
When the effect of this process and the flow of the current starts flowing more, the resistance of the device decreases.

* Characteristics of LDR
  
The light-dependent resistor is very responsive to light. When the light is stronger, then the resistance is lower which means, when the light intensity increases then the value of resistance for the LDR will be decreased drastically to below 1K.

<img width="300" height="206" alt="image" src="https://github.com/user-attachments/assets/c29a8942-8e63-437c-b02c-2b0004d995cc" />


When the light drops on LDR, the resistance will be decreased and when the resistor is placed in the dark then the resistance will be increased which is called dark resistance. 
If any device absorbs light then its resistance will be reduced radically. If a stable voltage is given to it, the light intensity will be increased & the flow of current starts increasing. 
So, the following diagram represents the characteristics between resistance & illumination for a specific LDR. 

LDRs are not linear devices and their sensitivity changes through the light’s wavelength which drops on them. Some kinds of photocells are not at all sensitive to a specific range of wavelengths because it depends on the used material.

Once light rays fall on a photocell, the resistance will be changed in 8 ms to 12, while it uses few more seconds to rise the resistance back again to its early value once the light is removed. So this is known as a recovery rate of resistance. 
In audio compressors, this property is applicable.

## Applications

* Automatic street lighting
* Campus lighting
* Parking-area lighting
* Garden lighting
* Energy-saving lighting systems

## Program:
```
int ldrPin = A0;
int ledPin = 9;
int ldrValue;
int threshold = 500;

void setup()
{
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  ldrValue = analogRead(ldrPin);

  if (ldrValue < threshold)
  {
    digitalWrite(ledPin, HIGH);
  }
  else
  {
    digitalWrite(ledPin, LOW);
  }

  delay(500);
}
```

## Circuit Diagram:
<img width="1483" height="1061" alt="image" src="https://github.com/user-attachments/assets/53e41ec4-6386-474d-bff9-cd3cbebb72ce" />


## Output:
<img width="1492" height="1054" alt="image" src="https://github.com/user-attachments/assets/614c9c22-1ede-49d5-88ee-13a0e98a0948" />



## Result: The Automatic Street Light Controller using LDR sensor was successfully designed and simulated in Proteus. The LED automatically turns ON when the surrounding light intensity decreases (darkness) and turns OFF when sufficient light is available.

