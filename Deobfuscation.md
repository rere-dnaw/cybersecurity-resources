# Deobfuscation
---
It a process of reviling obfuscated piece of code. 

### Online js console: https://jsconsole.com/

| minification    |  deminification  |
|:--------------:|:-----------:|
| https://www.toptal.com/developers/javascript-minifier | https://prettier.io/playground/ |
|| https://beautifier.io/ |

| Obfuscator    |  Deobfuscator  |
|:--------------:|:-----------:|
| https://beautifytools.com/javascript-obfuscator.php | http://www.jsnice.org/ |
```javascript
eval(function(p,a,c,k,e,d){e=function(c){return c};if(!''.replace(/^/,String)){while(c--){d[c]=k[c]||c}k=[function(e){return d[e]}];e=function(){return'\\w+'};c=1};while(c--){if(k[c]){p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c])}}return p}('5.4(\'3 2 1 0\');',6,6,'Module|Deobfuscation|JavaScript|HTB|log|console'.split('|'),0,{}))
```
#### Note: The above type of obfuscation is known as "packing", which is usually recognizable from the six function arguments used in the initial function "function(p,a,c,k,e,d)".

## Advanced obfuscators 
http://www.jsfuck.com/
https://utf-8.jp/public/jjencode.html
https://utf-8.jp/public/aaencode.html
https://obfuscator.io/

## Encoding code: 
Obfuscation can be also obtained by using encoding. In that situation the code will contain encoded text blocks that get decoded upon execution.

## Common Text encoding methods:
- ### base64
	- It's encoding which contains only 64 alphanumeric characters with addition of `+` and `/`. 
	- encoding **ASCII** to **base64**.
		- **ASCII** character is represented in 8 bit. **base64** is taking three ASCII characters and add their bits together (8 + 8 + 8 = 24). Then 24 bits is divided by 6 so from 3 **ASCII** characters we get four **base64** characters based on **base64 table**.    
	- spotting **base64**
		- `=` used as padding
		- the length of **base64** string has to be in a multiple of four
- ### Hex
	- It's encoding which is using **ASCII** character table number and encode it using only hex values (0-9 ans a-f). 
		- encoding **ASCII** to **HEX**
			- Find number for character in **ASCII** table and convert it to **HEX** by dividing number by 16
	- spotting **HEX**
		- the string contain only **0-9 ans a-f** values.
- ### Rot13(Caesar)
	- Shifts each letter by a fixed number. The **Rot13** shifts characters by 13 in forward direction.
- ### Useful tool to detect encoding type:
	- https://www.boxentriq.com/code-breaking/cipher-identifier

# Commands
| **Command** | **Description** |
|:--------------|:-----------|
| `echo text_to_encode \| base64` | base64 encode |
| `echo ENCODED_B64 \| base64 -d` | base64 decode |
| `echo text_to_encode \| xxd -p` | hex encode |
| `echo ENCODED_HEX \| xxd -p -r` | hex decode |
| `echo text_to_encode \| tr 'A-Za-z' 'N-ZA-Mn-za-m'` | rot13 encode |
| `echo ENCODED_ROT13 \| tr 'A-Za-z' 'N-ZA-Mn-za-m'` | rot13 decode |