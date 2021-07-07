#  Catholic Bible Reference Parser ✝️

## 💖 Vanilla JS Bible reference parser. 📜 Fast. Cross-browser compatible. Supports IE6+

**Visit the Demo page:** https://gryleader.github.io/catholic-bible-parser/lib/parser-demo.html

How to use:

1️⃣  Add the library scripts to your HTML file (commonly in the head section)

```javascript
<script type="text/javascript" src="biblebooks.js"></script>
<script type="text/javascript" src="bibleparser.js"></script>
```

2️⃣ Create a new **BibleParser** object and call its *parseText()* method:

```javascript
<script type="text/javascript">
	var bp = new BibleParser();		
	
	if (bp.parseText(astring)) {
		//bp.validRefs now contains an array of objects with the references found in astring		
		alert(bp.validRefs[0].ref);
	}	
</script>
```

### parseText(astring, vtype)

**Parameters:**

astring: input string

vtype: (optional. default="bcv") string with validation type can be one of "b" "bc" "bcv" or "bcva"

- "b": validates book names and prefix number      
- "bc": also validates chapter numbers
- "bcv": also validates verse numbers
- "bcva": also validates "addendum" verses e.g. Genesis 1:4-7.9.11 (".9.11")
      
**Result** 

Boolean: true or false. Returns true if it found at least one valid reference.
The references are stored in validRefs property as arrays of objects. This is an example of two references objects:

```javascript
validRefs[0]: {
"pos":"0-7",
"ref":"Gen2:21a",
"bookID":1,
"book":"Genesis",
"bookshort":"Gen",
"chapter":"2",
"verse":"21a"
}
validRefs[1]: {
"pos":"9-29",
"ref":"Gen 24:34-37.38.56ab",
"bookID":1,
"book":"Genesis",
"bookshort":"Gen",
"chapter":"24",
"verse":"34",
"rangeto":"37",
"addendum":".38.56ab"
}
...
```

### More info and Other methods:

**allowsections** property

Set allowsections to true after creating a BibleParser object if you want to include verse section letters in verses e.g. "12ab" in (Genesis 2:12ab). *(This property doesn't affect validation, only affects the string of the verses.)*

```javascript
//use allowsections if you want to enable capture of verse sections (e.g. Genesis 2:12ab)   
// if true verse == "12ab"	if false (default) verse == "12"
bp.allowsections = true;
```

**hasRefs()**

Returns a boolean. True if validRefs is populated with valid references after parseText was called. 

**refCount()**

Returns the number of valid references parsed and saved in validRefs after a call to parseText().

**logRefs()**

Returns a formatted HTML string with all the references and their data.

## Support / Tips

[![paypal](https://github.com/gryLeader/gryleader.github.io/blob/Main/imgs/paypalme.png)](https://paypal.me/EzequielMayan)

Thanks for your support! It will allow me to continue developments and start new projects. Blessings.

*«I will bless them that bless thee, and curse them that curse thee, and in thee shall all the families of the earth be blessed.»* (Gen. 12:3)
