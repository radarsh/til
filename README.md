# Today I Learned

A collection of TILs heavily inspired from [jbranchaud](https://github.com/jbranchaud/til).

## 20/07/2017 - IntelliJ Gradle dependency pasting

If you are looking to convert a Maven style dependency into Gradle style for use in your `build.gradle`, look no further. All you have to do copy something that looks like the below.

```xml
<dependency>
  <groupId>net.logstash.logback</groupId>
  <artifactId>logstash-logback-encoder</artifactId>
  <version>4.11</version>
</dependency>
```

When you past it inside the `dependencies` block of your `build.gradle`, it gets automatically converted to the below format by intelligent IntelliJ.

```
compile 'net.logstash.logback:logstash-logback-encoder:4.11'
```

## 7/11/2016 - Bash readline arguments

I discovered this one by accident. Simply open Bash and type <kbd>Alt + `digit`</kbd> followed by any character and you'll find the character repeated `digit` times on your prompt.

More about this at http://stackoverflow.com/questions/562115/press-alt-numeric-in-bash-and-you-get-arg-numeric-what-is-that

## 14/03/2016 - CSS3 ch unit of measurement

This can be invaluable if you are trying to express the width of an element as a multiple of the character width.
The best part is that `ch` understands the changes in character width arising due to different font styles, sizes etc.

Example:

```css
.panel {
    font-style: Consolas, monospace;
    font-size: 12px;
}

.drawer {
    width: 10ch;
}
```

```html
<div class="panel">
    <p>1234567890</p>
    <div class="drawer"></div>
</div>
```

The above will render both the `p` and the `div.drawer` elements at equal widths (provided the margins and paddings are set accordingly, of course).

What's more, the browser support for this is remarkably good too.

## 10/03/2016 - JavaScript input event

This is a robust way to handle changes to values of `input` and `textarea` elements. Browser support is excellent too. 

Example:

```javascript
$("input.class-name").on("input", function(e) {
    console.log("Value: ", $(this).val());
});
```

Before finding out about this, I was using the `keyup`, `keydown` and `keypress` events but each one comes with its own set of limitations. For instance, the `keyup` and `keydown` events don't filter out special keys such as `Ctrl` and `Alt`. The `keypress` isn't even a standard event and it gets tricky if you want to grab the value of a field after the key has been pressed.

## 26/02/2016 - Gradle offline mode

Extremely handy when you have to execute a Gradle task without connecting to the internet or remote repositories in situations such as when you're in a coffee shop or have no access to the network but have already downloaded all the dependencies. 

Simply use the `--offline` switch in conjunction with your task commands. 

Example:

```bash
$ gradle clean build --offline
```

Just keep in mind that it will only work if you have already downloaded all the required dependencies when you had access to the network. 
