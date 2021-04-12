# feedback-filler-lite

Simple Python for custom feedback filling

First let's get the dependancies straight
```bash
pip install keyboard
```

In a terminal open a python intrepreter with `sudo python` (or `python3` depending upon how you set your alias or whatever). Test out your import using ```import keyboard```

Most probably you got an import error(if you didn't, skip this step). This error is due to alias mismatch for the curious folks. Type in the command below and you'll get a path.

```bash
which python (or which python3)
/home/some/weird/bin/python
```

and then ```sudo /home/some/weird/bin/python``` and import keyboard. Viola! it should be working now

Fire up chrome, login into erp and open the feedback fill form. Select a course and a professor.

For the first one we'll fill it manually and let python remember it and then make it do the rest. But the catch is you can only use the keyboard to do everything. I'll give you tips if you aren't a keyboard wizard don't worry.

First let's make sure of two things
1. Pressing Alt+Tab once makes you switch between terminal and erp page (if you didn't know pressing Alt+Tab once takes you to the last used window)
2. The first option is selected (i.e good, very good or whatever)

Now

```
>>> fill = keyboard.record(until ='Esc')
```

Press Alt+Tab to switch to the erp page. Press tab to move to next option, right arrow or left arrow to move around through options, Enter to select it and Tab to move down(Shift+Tab to move up if you missed something). Fill up options and write generic strengths or weaknesses until you get to the captcha. Now press Esc. All your keystrokes are now recorded. Fill in the captcha and submit

Now it's time for python to work, select another professor
Make sure our two pre-requistes are again checked(Alt+Tab switches, first option checked)
run
```
>>> keyboard.play(fill, speed_factor = 3)
```
Fill the captcha and submit. 


Rinse and repeat
