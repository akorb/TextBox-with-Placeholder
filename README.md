# PlaceholderTextBox


In many cases it's very nice to use a placeholder instead of a label explaining the content.
With HTML5 this is very easy and just a single attribute. Unfortunately, no .NET control provides any similar attribute.

There are already two methods to do that.

#### Method 1
Windows has a build in function for adding a placeholder. To use it, you have to use P/Invoke.    
See StackOverflow: http://stackoverflow.com/questions/4902565/watermark-textbox-in-winforms

This has a slightly different behavior than all other methods. If you click on the text box a second time, the placeholder disappears. If you then leave the control with the mouse, it will be shown again. No option to change this, but I doubt that's a problem.

#### Method 2
This method is pretty clever. The placeholder actually isn't inside of the text box, it's just drawn over it.    
See CodeProject: http://www.codeproject.com/Articles/319910/Custom-TextBox-with-watermark

### Overview

| Method 1  | Method 2  | Mine |
| --------- |-----------| -----|
| Build-in  |Customizable|Customizable|
|           |           | Mono |

**Mono support**     
Method 1 obviously doesn't work with Mono because it uses the Win32 API.     
Method 2 throws an exception.     
Mine works almost perfect. Only the cursor is able to move through the placeholder with clicking. I don't know why yet.     

**Customizable**      
Method 1 is 0% customizable.      
Method 2 is very well customizable. Additional to mine it can set the placeholder color while focused.       
Mine can do the same as Method 2, except setting the color while focused (is this really necessary?).

**Recommendations**     
Use Method 1 if you only want to support Windows, like its behavior and the default light grey color is fine.    
Use Method 2 if you only want to support Windows and to set the color of the placeholder while focused.    
Use mine method if you want to support cross plattform.
