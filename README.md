See index.html or http://t7g.mods4ever.com/

Here's how I created this:

```
wget -rc --accept-regex '.*famvandermeer.demon.nl.*' https://web.archive.org/web/20220410211802if_/http://www.famvandermeer.demon.nl/7guesthomepage/open.html

find ./web/ -type f -print0 | xargs -0 mv -t 7guesthomepage/

```

Then I used VSCode to find and replace:

```
onmouseover="(.*)" onmouseout="(.*)"
```

to

```
xonmouseover="$1" xonmouseout="$2"
```

Because Wayback Machine didn't backup the mouseover images.

And Also replaced

```
"/web/.*/http://www.famvandermeer.demon.nl/7guesthomepage/
```

to just

```
"
```

And in open.html I changed the `<frameset rows` sizing
