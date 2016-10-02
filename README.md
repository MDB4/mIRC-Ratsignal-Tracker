# FuelRats-mIRC-Ratsignal-Tracker
Novice/hobbyist work in progress. Warning: this code may burn retinas and/or infuriate you.

# Installation
Copy fuelrats.ini to your mIRC script folder, open the script editor (alt+r), click File->Load (ctrl+l), locate & open fuelrats.ini.

## Features (bugs?)
Parses ratsignals, stores details in hashtables, logs to a window, keeps a listbox populated with current cases.
  Cleared case details additionally include clear time, case duration, 1st limpet, and paperwork. Referenced upon new signals to indicate repeat clients >:D

Upon each new ratsignal, the reported system name is copied into the clipboard. This is the original idea that spawned this script; I didn't want to tab out of game to copy the system name.   
Many thanks to Clapton for giving me a nice regex function to parse out the system name, which I then modified to grab additional info from the signal, and now I have this hideous script.

If you get 1st limpet on a case, and your IRC Nick is mentioned in the clear line reported by MechaSqueak[BOT], a browser window will open the paperwork link automatically. TODO: make this toggleable.

New Ratsignals are displayed in the left pane of the @Ratsignal window as follows:   
 **[TIME] CMDR • Case # • Platform • System • Language**

Current cases are listed in a listbox in the right pane of the @Ratsignal window, sorted newest first:   
 **CMDR | Case # | Platform | System | Language | Signal Time**

Cleared cases are displayed in the left pane of the @Ratsignal window as follows:   
 **[TIME] CMDR • Case Duration • 1st Limpet • Paperwork**

When a !clear is done on a matching case, it's removed from the active hashtable and the listbox, and stored in the cleared hashtable.

## @Ratsignal custom window right-click context menu lists:
- Current "quiet" duration: time since last signal, and the maximum quiet record
- Cases in the past 1hr, and the maximum 1hr record
- Cases in the past 24hrs and the maximum 24hr record
- Embedded in the 24hr record entry, is a list of the number of cases in each of the previous 24 hours
- Text-to-speech options for audible notification of Ratsignals, PC, Xbox, and Code Red.

## Known issues
- I have zero programming / scripting training. Many functions are written poorly and are probably inefficient.
- Relies on constant connection to fuelrats irc. i.e: no shutting down mIRC when you're done for the day.
- If the script is loaded when the board is not clear, those current cases will obviously not have thier origin details logged upon !clear.
- !CMDR & !SYS used in PM do not broadcast to channels, these will be missed.
- A board refresh in and of itself shouldn't prevent !clear tracking, but if new cases come in before all existing cases at the time of a refresh have been cleared, and !CMDR is used on a case, I'll lose track of the new CMDR.
- I probably forgot some things as well

## Unknown issues
 Likely exist
