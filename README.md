# Zap CSS Tools
I've had a bookmarklet sitting around my browser since 2002. Once in a while I use it. I've decided to upgrade and combign a few ideas:

* Bookmarklet to kick off the zapping
* Repository to hold personlization css

## Zap CSS Bookmarklet
Combign three activities into one javascript file

* Remove all css
* Remove images
* Apply Reboot/Normalize CSS
* Apply Personalized CSS

## Personalized CSS
After reboot and normalize, the `personalize.css` file applies very simple formatting like borders to a page.

## Using
* Create a new bookmark
* Set the name to `Zap CSS`
* Set the value to 
```javascript
# Zap CSS
javascript:(function(){var i,x;for(i=0;x=document.styleSheets[i];++i)x.disabled=true;})();

# Zap Images
javascript:(function(){var imgs=document.getElementsByTagName("img"),frames=document.getElementsByTagName("iframe");for(var i=0;i<imgs.length;i++)imgs[i].style.display="none";for(var i=0;i<frames.length;i++)frames[i].style.display="none"}());

# Reboot CSS
javascript:(function(){var head = document.getElementsByTagName('head')[0];var style = document.createElement('link');style.href = 'https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.5.0/css/bootstrap-reboot.css';style.type = 'text/css';style.rel = 'stylesheet';head.append(style);})();

# Combined and minimized

javascript:(function(){var i,x;for(i=0;x=document.styleSheets[i];++i)x.disabled=!0;var imgs=document.getElementsByTagName("img"),frames=document.getElementsByTagName("iframe");for(i=0;i<imgs.length;i++)imgs[i].style.display="none";for(i=0;i<frames.length;i++)frames[i].style.display="none";var head=document.getElementsByTagName("head")[0],style=document.createElement("link");style.href="https://raw.githubusercontent.com/briglx/zap_css_tools/main/zapcss.min.css",style.type="text/css",style.rel="stylesheet",head.append(style)}());
```

# Development

Take the javascript and minimize it

```javascript

javascript:(
    function(){

        var i,x;for(i=0;x=document.styleSheets[i];++i)x.disabled=true;
        var imgs=document.getElementsByTagName("img");for(i=0;i<imgs.length;i++)imgs[i].style.display="none"
        var frames=document.getElementsByTagName("iframe");for(i=0;i<frames.length;i++)frames[i].style.display="none";
        var svgs=document.getElementsByTagName("svg"),for(i=0;i<svgs.length;i++)svgs[i].style.display="none";
        var head = document.getElementsByTagName('head')[0];
        var style = document.createElement('link');
        style.href = 'https://raw.githubusercontent.com/briglx/zap_css_tools/main/zapcss.min.css';
        style.type = 'text/css';
        style.rel = 'stylesheet';
        head.append(style);

    })();
```

Replace the comment with the minimized output:

```javascript
javascript:(function(){<!--  Place here -->})();
```
