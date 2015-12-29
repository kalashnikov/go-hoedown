# go-hoedown

This is Go-bindings for [Hoedown](https://github.com/hoedown/hoedown) Markdown parser.

## Usage

```go
package main

import (
        "github.com/kentaro/go-hoedown"
        "os"
)

func main () {
    parser := hoedown.NewHoedown(map[string]uint{
        "extensions":  hoedown.EXT_NO_INTRA_EMPHASIS | hoedown.EXT_AUTOLINK,
        "renderModes": hoedown.HTML_USE_XHTML | hoedown.HTML_ESCAPE,
    })
    parser.Markdown(os.Stdout, []byte("# Hoedown"))
}
```

### Extensions

+ `EXT_AUTOLINK`: Automatically parse URLs into links.
+ `EXT_DISABLE_INDENTED_CODE`: Disables indented code blocks.
+ `EXT_FENCED_CODE`: Enables fenced code blocks.
+ `EXT_FOOTNOTES`: Enables [Markdown Extra style footnotes][syntax-footnotes].
+ `EXT_HIGHLIGHT`: Enables ==marking== text.
+ `EXT_LAX_SPACING`: Removes the need for an empty line between Markdown and raw HTML.
+ `EXT_NO_INTRA_EMPHASIS`: Disables emphasis_between_words.
+ `EXT_QUOTE`: "Quotes" are translated into `<q>` tags.
+ `EXT_SPACE_HEADERS`: ATX style headers require a space after the opening number sign(s).
+ `EXT_STRIKETHROUGH`: Enables \~~striking~~ text.
+ `EXT_SUPERSCRIPT`: Enables super\^script.
+ `EXT_TABLES`: Enables [Markdown Extra style tables][syntax-tables].
+ `EXT_UNDERLINE`: Translates `<em>` tags into `<u>` tags.

### Render flags

+ `HTML_ESCAPE`: All HTML is escaped.
+ `HTML_EXPAND_TABS`: Tabs are expanded to spaces.
+ `HTML_HARD_WRAP`: Line breaks are translated into `<br>` tags.
+ `HTML_SAFELINK`: Only links to safe protocols are allowed.
+ `HTML_SKIP_HTML`: All HTML tags are stripped.
+ `HTML_SKIP_IMAGES`: Images are ignored.
+ `HTML_SKIP_LINKS`: Links are ignored.
+ `HTML_SKIP_STYLE`: `<style>` tags are stripped.
+ `HTML_SMARTYPANTS`: Enables SmartyPants.
+ `HTML_TOC`: Anchors are added to headers.
+ `HTML_USE_XHTML`: Renders XHTML instead of HTML.
+ `HTML_PRETTIFY`: Add `<code class="prettyprint xxx">` into code section. Need to replace into `language-` for [prism.js](https://github.com/PrismJS/prism)

## See Also

  * [Hoedown](https://github.com/hoedown/hoedown)
  * [Goskirt](https://github.com/madari/goskirt)
    * Go-bindings for Sundown Markdown parser

## Author

  * [Kentaro Kuribayashi](http://kentarok.org/)

## License

  * MIT http://kentaro.mit-license.org/

