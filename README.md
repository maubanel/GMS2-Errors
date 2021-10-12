<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### GMS 2 Errors

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

This tutorial is intended for those wanting an introduction to <i>GameMaker Studio 2</i> using their scrpting language <i>GML</i>. This assumes no prior knowledge of the software or scripting. This walk through looks at errors.  There are three kind of errors:

* Compile errors.  This is where the game does not compile so it cannot be run.  Often this is just a simple spelling mistake.

* Runtime errors.  These are errors that appear when playing the game.  These can be a bit trickier to track down.

* Logical errors.  These never break, crash or cause any warnings in the game.  They are just plain mistakes or wrong - resulting in an unwanted behavior.  Often we refer to these as bugs.

#### Software Needed
* Tested on GameMake Studio2.3.5.589
* An existing [GML Project](https://github.com/maubanel/GMS2-Snippets/blob/main/rename-project/README.md#user-content-rename-gms2-project)

<br>

---


##### `Step 1.`\|`ITB`|:small_blue_diamond:

Lets create a new room by *right-clicking* on **Rooms** in the **Asset Browser** tab and selecting **Create | Room**.  Call it `rm_errors`. Move the room to the top in the **Room Order** menu.

![Create new room called rm_errors and move to top of room order](images/AddRmErrors.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Right click on **Objects** title in the **Asset Browser** folder.  Select **Create | Object** and call it `obj_errors_controller`.

![Create new object called obj_errors_controller"](images/ObjErrorsController.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`ITB`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets start with heads up display (HUD) for this room.  Press the <kbd>Add Event</kbd> button and select a **Draw | Draw** event.

![Add draw event to obj_errors_controller](images/AddDrawEventToObjErrorsContr.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`ITB`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Type the following script in the newly created draw script.  Please mispell `draw_text` on purpose to show what happens if you mispell a function name.

![mispell draw_text function](images/DrawRoomTitleMispelledFunction.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`ITB`| :small_orange_diamond:

*Double left click* on **rm_errors** to open the room and *drag and drop* the **obj_errors_controller** object into the room.

![Draw obj_errors_controller to outside of room](images/DragErrorsControllerInRoom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`ITB`| :small_orange_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. This time the game never runs.  At the very bottom there should be a tab whose title is Compile Errors.  Inside it reads the message `Object:obj_errors_controller Event:Draw at line 7: unknown function or script draw_tetx`.  Sometimes the errors can be a bit obtuse other times there are very precise.  Now we know which object, which event type and what line our error is in.

![Run game but compile errors inhibits game from starting](images/CompileErrorWrongFunction.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`ITB`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

OK, lets fix the spelling mistake.  Please notice the color change in the editor. If you are using a gamemaker function or variable it will be an orange color and this is one tip that something is wrong. This only works for GML supplied names, as the ones we create ourselves will never be orange.

![Look at color of built in variable names and functions](images/DrawTextSpellingFix.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`ITB`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now it loads the game up again.  This was the first type of error we will get in gamemaker a compile error. It means the compiler stops us from running the game as it has a problem trying to build the game executable.

![Game loads properly once spelling is fixed and title is displayed](images/RoomOfErrorsSmallTitleInGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`ITB`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now lets look at some more errors.  Lets make the font a bit larger.  *Right click* on the **Fonts** title in the **Asset Browser** menu.  Select **Create | Font** from the menu and name the new font `fnt_title`</tt.> Change the **Style** to `Bold` and the **Size** to `24`.  This will be twice the size as the previous version.

![Create a title font](images/CreateTitleFont.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`ITB`| :large_blue_diamond:

Now reopen the **obj_errors_controller:Draw** event script and change the font before the draw text with a new function called **[draw_set_font(font](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Drawing/Text/draw_set_font.htm)**.

![Change font type for title in obj_errors_controller draw event](images/InsertFontTitleIntoScript.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`ITB`| :large_blue_diamond: :small_blue_diamond: 

Now mispell the font name in the parenthesis.  Look at what happens to the color of it?  Not only does GameMaker color its own variables and functions it also colors red resource names that it recognizes that you added to the resource list.  In this case if we don't spell it, it will look for a variable holding a font. OK, change the spelling back to fnt_title and fix the spelling error.  

![Change font name to be wrong](images/MispellFontTitle.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`ITB`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`ITB`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`ITB`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`ITB`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`ITB`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`ITB`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`ITB`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`ITB`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`ITB`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`ITB`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

| `gms2.variables`\|`THE END`| 
| :--- |
| **That's All Folks!** That's it for variables. |

___

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=The End!">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

