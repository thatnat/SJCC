# SJCC
Simple Java Canvas Controls
## Download
Latest release can be found [here](https://github.com/thatnat/SJCC/releases/tag/v1.0.0)
## What is it?
SJCC is a simple one-class library for creating a render method, along with all you'll need for inputs:  
- Keyboard
- Mouse
- Mousewheel

## Why use it?
It is _**really, really**_ lightweight.  
I don't mind if you don't give credit for using this.
## How do you use it?
```java
import java.awt.Graphics2D;
import java.awt.event.KeyEvent;
import java.awt.event.MouseEvent;

import sjcc.SJCC;

public class TestWindow extends SJCC {
  
  public static void main(String[] args) {
    TestWindow t = new TestWindow();
    t.WIDTH = 800; //Example
    t.HEIGHT = 600;
    t.TITLE = "Test Window";
    t.start();
  }

  @Override
  public void render(Graphics2D g, double delta) {
    //Put anything in here you want
    if (getMouseWheel() != 0) {
      System.out.println("Mouse wheel moved!");
    }
    if (getKey(KeyEvent.VK_SPACE) == 0) {
      System.out.println("Space just pressed!");
    }
    if (mousePressed()) {
      if (mouseButton() == MouseEvent.BUTTON1) {
        System.out.println("Left mouse button pressed at " + 
        clickMousePoint().x + ", " + clickMousePoint().y);
      }
    }
  }

}
```
#### Things to note with mouse
clickMousePoint() returns the position of a mouse click, whilst currentMousePoint() returns the current position of a mouse click. mousePressed() returns true if it was *just* clicked and mouseDown() returns ture if the mouse is down.
All mouse positions are realative to the canvas.
getKey() returns a double representing the time it has been held down for.
