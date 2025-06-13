# IDEA_9103_Tut02_groupC_jguo4020_user_input  
## Interaction Instructions
- The artwork is stationary by default to replicate the original piece.
- Clicking on any disc with the mouse will start or stop its rotation. Pressing the spacebar will start or stop the rotation of all discs. 
- Using the arrow keys, you can control the rotation speed and direction of the last operated disc (the one last clicked with the mouse, or all discs if the spacebar was used most recently).
    - The up arrow increases the rotation speed, the down arrow decreases it, the left arrow sets the rotation to counterclockwise, and the right arrow sets it to clockwise.
- The light rings surrounding the discs will begin to "flow" as the discs rotate. The more discs are rotating and the faster they spin, the quicker the color changes in the light rings. 
- If you wish to restore the artwork to its original state, press the "C" key to clear all rotation states and reset the positions and colors to default.
## Animation
- Interaction Approach
    - For my part, I choosed user input as interaction approach.
- Animated Properties
    - The animation enables the discs in the artwork to rotate under user control, while the light-strip-like color chains around them create a "flowing" effect in response to the rotation. Unlike my teammates, I designed the discs as independently controllable elements and made the surrounding color bands flow accordingly.
## Inspirations
- The inspiration for this animation comes from the visual and conceptual resemblance between the circular structures in the original artwork and galaxies. The similar yet distinct rings reminded me of the countless celestial bodies scattered throughout the universe. While their structures follow certain patterns, they differ greatly in detail.</br>
    ![Galaxy rotation](galaxy.gif)</br>
    The rotation of the discs in the artwork echoes the spiral motion of celestial bodies in the universe, where individual planetary systems or star clusters rotate at different speeds and in different directions. This connection inspired the idea of making each disc independently controllable, creating a scene reminiscent of galaxies spinning in space.
- The inspiration for making the color bands surrounding the discs “flow” comes from energy trails or magnetic fields, which often visually accompany the motion of celestial bodies. These light bands are not static; instead, their continuously shifting colors and flow speeds reflect underlying dynamic changes, just like in astronomical phenomena, where rotation can produce observable trails, displacements, or energy pulses.
    ![Space magnet](magnet.gif)
    Beyond its visual resemblance to the cosmos, the inspiration for the animation’s interactivity also stems from the relationship between humans and the universe. Over 90% of the atoms in the human body originate from stars, one could say we are descendants of stardust. Much like the universe itself, a collective is made up of many similar yet distinct individuals. While each person’s actions or fate may be self-directed, they are also influenced by larger collectives or societies.
##  Technical Explanation
This animation was implemented using the p5.js framework. The code follows an object-oriented approach, with each rotating disc represented by an instance of the `RingPattern` class. The sketch initializes multiple discs using a configuration array (`ringConfigs`), which defines their positions, fill styles, colors, pattern types, and optional settings such as curves or angles.
### 1. Disc Rotation Logic
- Each disc (`RingPattern`) contains an internal angle and a rotation speed variable. When a user clicks on a disc, the `getBoundingClientRect()` method is used in combination with `clientX` and `clientY` to determine which disc was clicked. The `isRotating` flag of that disc is then toggled, and the disc is added to the `operatingRings` array, which tracks the most recently operated discs. In the `draw()` function, the rotation state is updated only for discs that are marked as rotating.
- The spacebar can toggle all discs simultaneously, updating their `isRotating` states and adding all of them to the `operatingRings` array. The arrow keys allow adjustments to the rotation speed (UP/DOWN) and direction (LEFT/RIGHT) of the discs in `operatingRings`. This design enables precise control, whether individually or collectively.
### 2. Color Band “Flow” Effect
The color bands surrounding each disc are visualized as chains of small, dynamically color-shifting ellipses. Their animation is linked to the rotation of the discs.When a disc rotates, the surrounding ellipses change color more rapidly. The animation speed is calculated based on the number of rotating discs and their combined rotation speed, creating a sense of energy and motion.

These flowing elements are rendered using the `fillEllipse()` function, which maps colors from a rotating palette (`fillColors`) and rotates each ellipse to simulate a continuous wave effect.
## Decelaration
ChatGPT was used to translate parts of the README and the group document.