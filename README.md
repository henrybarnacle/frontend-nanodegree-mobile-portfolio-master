## Website Performance Optimization portfolio project


###Part 1: Optimize PageSpeed Insights score for index.html

Step 1 - Install ngrok and test index.html on Pagespeed Insights.

####Goal: 90/100 Pagespeed score
####Current State: 27/100 Mobile, 29/100 Desktop

Step 2 - Optimize Images. Took web hosted images and hosted them locally. Resized all using Photoshop to be correct pixel dimensions and then compressed to optimal size using tinyjpg.com.

Step 3 - Installed Grunt Critical Task runner to find and inline critical CSS. 

**Installed latest versions of node.js, npm and grunt globally**

**Created Package.json and Gruntfile.js files in the project directory**

**Installed the grunt critical task runner in the project directory**

**Enabled the critical task inside the Gruntfile**

**Ran Grunt Critical to create the new index.html file with inlined crtical CSS and then copied the changes over to the original index.html file**

Step 4 - Eliminated other render blocking properties, media screen for print.css.

Step 5 - Minified index.html and css.

####Result: 93/100 Pagespeed score for Mobile & Desktop.

###Part 2: Achieve a framerate of 60FPS for pizza.html.

####Goal: Scrolling Jank free and achieving 60FPS. Less than 1MS Average scripting time to generate last 10 frames: 
####Current State: Lots of jank, around 7 FPS. More than 100MS Average scripting time to generate last 10 frames: 

Step 1 - On line 531 of main.js, reduced the number of pizza images being generated on scroll from 200 to 30.

Step 2 - Compressed the pizza.png image with tinypng.com to 3KB. Also optimized the pizzeria.jpg to be 90% smaller just in case.

Step 3 - Edited the updatePositions function by pulling sereral calculations out of the 'for loop' and estabishing them as variables beforehand. This reduced the amount of calculating the loop needs to do every time it runs.

Step 4 - Added the CSS property 'will-change' to the .mover class. Also added the 'translateZ(0)' hack to updatePostions. I'm not sure 100% if this is need as well as the 'will-change' property being added to css but with both changes the scrolling seemed smoother.

Step 5 - Added requestAnimationFrame to the updatePostions call at the end of the file.

####Result: Jank is gone , achieving 60FPS. Around 0.45MS Average scripting time to generate last 10 frames: 

###Part 3: Achieve pizza resize in under 5 ms.

Step 1 - Edited changePizzaSizes function to take the timely calculations out of the loop and estalish the variables before looping. Establishing the new dimensions of the pizza container before the loop which changes all the pizzas and containers sizes to the new dimensions.

####Result: Success- time to resize is now under 5MS.

