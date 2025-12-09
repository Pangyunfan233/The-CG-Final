The CG-Final of Pac-Man

<img width="1197" height="545" alt="image" src="https://github.com/user-attachments/assets/1a454ef7-576a-4a62-8f4b-1f57feb847a9" />




The Holograms Shader
<img width="735" height="399" alt="image" src="https://github.com/user-attachments/assets/414b9691-a62e-4484-b40c-9d871e19987a" />
<img width="707" height="435" alt="image" src="https://github.com/user-attachments/assets/e00e30cf-4e31-4f83-bb03-307309582525" />

In the creation process, I used the Holograms shader on Blinky, as shown in the image. I created a red, virtual projection-like effect. The principle is to determine the viewing effect using dots in the normal vector direction and the view direction. Then, I set the shader's initial settings to transparent and always perform a depth test. Next, I concatenated the dot results to a one-minute interval to obtain the emission effect. Then, I concatenated the Ecolor values ​​using multiply, and used a power node to fill the entire object with the emission color. Finally, I output the emission color. Then, I output the main binky color and concatenated it with a float to add alpha values, which is used to clip the object.



The Scrolling texture
<img width="1201" height="558" alt="image" src="https://github.com/user-attachments/assets/8f98d3af-57f4-40de-9ea3-aa9544974abb" />
<img width="762" height="550" alt="image" src="https://github.com/user-attachments/assets/6b22db5a-6c0c-4feb-a8ed-1310d6ae86c2" />

For the scrolling shader, I chose a starry sky background image because I wanted the background to appear as if stars were twinkling in the universe. First, I used a time node, similar to `time.deltatime` in programming, which changes over time. Then, I multiplied a float to control the speed of the time. Next, I output to the tiling and offset node, which is a constantly changing and moving offset node—the main part of this scrolling shader. Then, I connected the animation and image using a sample texture. Finally, I used multiply to connect the star colors and output the final color.




Two additional textures 

The simple diffuse-specular shader
<img width="1195" height="555" alt="image" src="https://github.com/user-attachments/assets/b84e97e1-7197-47c5-acda-8e497d5e7d8e" />
<img width="493" height="244" alt="image" src="https://github.com/user-attachments/assets/8132bbb4-633c-423e-8ae9-1bbdba8131ad" />

First, I chose the simple diffuse-specular shader for the player because I wanted the player's color to move with them, with different effects in different channels to indicate their viewpoint and the position of the light source. I also personally think this makes the player look better, using contrasting yellow and orange. In creating this shader, I first used the normalize property of the main light node and the normal vector to dot the color change caused by the light source direction and object position. Then, I connected these normalize properties to the reflection node, which tells us the relationship between color and brightness based on the light source and object position. Next, I used the view direction and reflection values ​​to dot the color when the object faces the shadow direction. Then, I used saturate to control the value range between 0 and 1. Then, I used a power node to determine the size of the highlight and shadow areas. Next, I multiplied a color, and finally added this color along with the highlight color to get a complete shader, which was then output.


The water shader
<img width="1191" height="555" alt="image" src="https://github.com/user-attachments/assets/630a55bc-f6e1-4794-b223-8ff3bb847e95" />
<img width="554" height="423" alt="image" src="https://github.com/user-attachments/assets/83c8bad2-758a-4503-9a0d-c74c1a704d89" />

Next, regarding the water shader, I wanted to add more restrictions on players and NPCs in the Pac-Man game, so I added water that players can walk through normally, but NPCs cannot. In creating the water, I initially used a time node and a float to multiply, obtaining a controllable speed change. Then, I connected this to a tiling and offset node to create an "animation." Next, I connected the result to a sample texture, changed the node's type to normal, and uploaded the water's normal map to it. Then, I output the result to the Fragment's normal map, created a normal sample texture, uploaded the water's texture to it, and connected it to the basecolor to output the result. This resulted in a water surface that appears to have depth and shimmering light.


The Bug issue
<img width="1208" height="565" alt="image" src="https://github.com/user-attachments/assets/e664b749-c87c-41c7-a06f-ce0be5187fb9" />
I don't know what the problem is, but when I reopen the game, the scrolling shader disappears from the game screen, like in the picture, but it still works in the shader graph.




