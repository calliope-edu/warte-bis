You will find the English ReadMe at the end of the document.

## Verwendung

### warten bis Taste gedrückt wird

Wartet, bis Taste A gedrückt wird, bevor die nächste Codezeile ausgeführt wird. Du kannst auch Taste B oder A + B wählen.

```blocks
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
```

### warten bis Taste losgelassen wird

Wartet, bis Taste A losgelassen wird, bevor die nächste Codezeile ausgeführt wird. Du kannst auch Taste B oder A + B wählen.

```blocks
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
```

### warten bis Pin gedrückt wird


Wartet, bis der gewählte Pin gedrückt wird, bevor die nächste Codezeile ausgeführt wird. Du kannst Pin 0, 1 und 2 wählen.


```blocks
WaitUntilBlocks.waitUntilPinPressed(TouchPin.P0)
```

### warten bis Pin losgelassen wird


Wartet, bis der gewählte Pin losgelassen wird, bevor die nächste Codezeile ausgeführt wird. Du kannst Pin 0, 1 und 2 wählen.


```blocks
WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
```

### warten bis Schallpegel unter Wert ist

Dieser Block kann nur mit einem Calliope mini 3 verwendet werden.

Wartet, bis der Schallpegel unter einem gewählten Wert liegt, bevor die nächste Codezeile ausgeführt wird.

```blocks
WaitUntilBlocks.waitUntilSoundLevelBelow(80)
```

### warten bis Schallpegel über Wert ist

Dieser Block kann nur mit einem Calliope mini 3 verwendet werden.

Wartet, bis der Schallpegel über einem gewählten Wert liegt, bevor die nächste Codezeile ausgeführt wird.

```blocks
WaitUntilBlocks.waitUntilSoundLevelAbove(80)
```

## Beispiele

Der benutzerdefinierte Block, der wartet, bis ein Pin losgelassen wird, ist nützlich beim Erstellen von Spielen, in denen du einen Stromkreis schließt, zum Beispiel durch das Werfen eines leitenden Balls in einen Korb, und der Stromkreis für mehr als 1 Sekunde geschlossen ist.

Er ist auch nützlich, wenn ein Ball etwas springt und den Stromkreis mehrfach schließt. In beiden Fällen funktioniert der reguläre "Bei Pin gedrückt" Block nicht.

```blocks
let score = 0
basic.showNumber(score)
basic.forever(function () {
    if (input.pinIsPressed(TouchPin.P0)) {
        score += 1
        basic.showNumber(score)
        WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
    }
})
```


Um eine schnelle Vorstellung davon zu bekommen, was die anderen Blöcke tun, kannst du diesen Code testen:

```blocks
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
basic.showIcon(IconNames.Yes)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
basic.showIcon(IconNames.Heart)
WaitUntilBlocks.waitUntilPinPressed(TouchPin.P0)
basic.showIcon(IconNames.Butterfly)
WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
basic.showIcon(IconNames.Duck)
WaitUntilBlocks.waitUntilSoundLevelBelow(80)
basic.showIcon(IconNames.Happy)
```

Du musst Taste A drücken und P0 berühren, bevor der Calliope mini einen Schall unter Pegel 80 erkennt und das glückliche Gesicht am Ende anzeigen kann. Der Vorteil der "warten bis" Blöcke ist, dass du keine Variable benötigst, um dies zu erreichen. Das macht es anfängerfreundlicher.

Diese Idee kann auch beim Erstellen eines Alarms verwendet werden, zum Beispiel mit ABBA als Geheimcode, was bedeutet, dass du Taste A drücken, Taste B zweimal drücken und A erneut drücken musst, um einen Alarm ein- oder auszuschalten.

```blocks
input.onButtonPressed(Button.A, function () {
    pushed_how_many_times += 1
})
input.onButtonPressed(Button.B, function () {
    pushed_how_many_times += 1
})
let pushed_how_many_times = 0
basic.showIcon(IconNames.No)
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
WaitUntilBlocks.waitUntilButtonPressed(Button.B)
WaitUntilBlocks.waitUntilButtonReleased(Button.B)
WaitUntilBlocks.waitUntilButtonPressed(Button.B)
WaitUntilBlocks.waitUntilButtonReleased(Button.B)
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
if (pushed_how_many_times == 4) {
    basic.showIcon(IconNames.Yes)
} else {
    basic.showIcon(IconNames.Sad)
}
```

Weitere Beispiele findest du in diesem Blog: https://tinker-club.blogspot.com/p/makecode-extension.html

## Als Erweiterung verwenden

Dieses Repository kann als **Erweiterung** in MakeCode hinzugefügt werden.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc)
* klicke auf **Neues Projekt**
* klicke auf **Erweiterungen** unter dem Zahnrad-Menü
* suche nach **https://github.com/teacherpinky/wait-until-blocks** und importiere

## Dieses Projekt bearbeiten ![Badge buildstatus](https://github.com/teacherpinky/wait-until-blocks/workflows/MakeCode/badge.svg)

Um dieses Repository in MakeCode zu bearbeiten.

* öffne [https://makecode.calliope.cc](https://makecode.calliope.cc)
* klicke auf **Importieren** und klicke dann auf **URL importieren**
* füge **https://github.com/teacherpinky/wait-until-blocks** ein und klicke auf importieren


#### Metadaten (verwendet für Suche, Darstellung)

* für PXT/calliopemini
* für PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>



## Usage

### wait until button is pressed

Waits until button A is pressed before the next line of code is executed. You can also choose button B or A + B.

```blocks
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
```

### wait until button is released

Waits until button A is released before the next line of code is executed. You can also choose button B or A + B.

```blocks
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
```

### wait until pin is pressed


Waits until the chosen pin is pressed before the next line of code is executed. You can choose pin 0, 1 and 2.


```blocks
WaitUntilBlocks.waitUntilPinPressed(TouchPin.P0)
```

### wait until pin is released


Waits until the chosen pin is released before the next line of code is executed. You can choose pin 0, 1 and 2.


```blocks
WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
```

### wait until sound level is below

This block can only be used with a Calliope mini 3.

Waits until the sound level is below a chosen value before the next line of code is executed.

```blocks
WaitUntilBlocks.waitUntilSoundLevelBelow(80)
```

### wait until sound level is above

This block can only be used with a Calliope mini 3.

Waits until the sound level is above a chosen value before the next line of code is executed.

```blocks
WaitUntilBlocks.waitUntilSoundLevelAbove(80)
```

## Examples

The costum block that waits for a pin to be released is useful when making games in which you close a circuit, for example by throwing a conductive ball in a basket, and the circuit is closed for more than 1 second.

It's also useful if a ball bounces a bit, closing the circuit a few times. In both cases the regular "On pin pressed" block doesn't work.

```blocks
let score = 0
basic.showNumber(score)
basic.forever(function () {
    if (input.pinIsPressed(TouchPin.P0)) {
        score += 1
        basic.showNumber(score)
        WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
    }
})
```


To get a quick idea of what the other blocks do, you can test this code:

```blocks
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
basic.showIcon(IconNames.Yes)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
basic.showIcon(IconNames.Heart)
WaitUntilBlocks.waitUntilPinPressed(TouchPin.P0)
basic.showIcon(IconNames.Butterfly)
WaitUntilBlocks.waitUntilPinReleased(TouchPin.P0)
basic.showIcon(IconNames.Duck)
WaitUntilBlocks.waitUntilSoundLevelBelow(80)
basic.showIcon(IconNames.Happy)
```

You have to press button A and touch P0 before the Calliope mini will detect a sound below level 80 and to be able to get the happy face at the end. The advantage of the "wait until" blocks is that you don't need a variable to make this happen. That makes it more beginner friendly.

This idea can also be used when making an alarm, for example with ABBA as secret code, meaning you have to press button A, press button B twice and press A again to put on or off an alarm.

```blocks
input.onButtonPressed(Button.A, function () {
    pushed_how_many_times += 1
})
input.onButtonPressed(Button.B, function () {
    pushed_how_many_times += 1
})
let pushed_how_many_times = 0
basic.showIcon(IconNames.No)
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
WaitUntilBlocks.waitUntilButtonPressed(Button.B)
WaitUntilBlocks.waitUntilButtonReleased(Button.B)
WaitUntilBlocks.waitUntilButtonPressed(Button.B)
WaitUntilBlocks.waitUntilButtonReleased(Button.B)
WaitUntilBlocks.waitUntilButtonPressed(Button.A)
WaitUntilBlocks.waitUntilButtonReleased(Button.A)
if (pushed_how_many_times == 4) {
    basic.showIcon(IconNames.Yes)
} else {
    basic.showIcon(IconNames.Sad)
}
```

More examples can be found on this blog: https://tinker-club.blogspot.com/p/makecode-extension.html

## Gebruiken als extensie

Deze repository kan worden toegevoegd als **extensie** in MakeCode.

* open [https://makecode.calliope.cc/](https://makecode.calliope.cc)
* klik op **Nieuw project**
* klik op **Extensies** onder het tandwielmenu
* zoeken naar **https://github.com/teacherpinky/wait-until-blocks** en importeren

## Dit project bewerken ![Badge buildstatus](https://github.com/teacherpinky/wait-until-blocks/workflows/MakeCode/badge.svg)

Om deze repository te bewerken in MakeCode.

* open [https://makecode.calliope.cc](https://makecode.calliope.cc)
* klik op **Importeren** en klik vervolgens op **Importeer URL**
* plak **https://github.com/teacherpinky/wait-until-blocks** en klik op importeren


#### Metadata (gebruikt voor zoeken, rendering)

* for PXT/calliopemini
  
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
