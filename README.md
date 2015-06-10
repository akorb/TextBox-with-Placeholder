# PlaceholderTextBox


In many cases it's very nice to use a placeholder instead of a label explaining the content.
With HTML5 this is very easy and just a single attribute. Unfortunately, no .NET control provides any similar attribute.

It actually can be done with a small hack:

```C#
private const int EM_SETCUEBANNER = 0x1501;

[DllImport("user32.dll", CharSet = CharSet.Auto)]
private static extern Int32 SendMessage(IntPtr hWnd, int msg, int wParam, [MarshalAs(UnmanagedType.LPWStr)]string lParam);
```

followed by
```C#
SendMessage(textBox1.Handle, EM_SETCUEBANNER, 0, "AnyPlaceholder");
```

But this placeholder disappears as soon as the user focuses the textbox.
And it's less to not customizable.

I want to create a simple control which fulfilles this need.

I have two destinations:
* **Simplicity**   
I implement it just like an actual Windows Forms control.

* **Customizable**   
You should be able to change the color of the placeholder.


Everybody is invited to contribute to this project, I would be very happy if this control is viewed by more than two eyes so it will work very well.
