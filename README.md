# MMM-HK-KMB
<B>Station monitor</B> for the <B>Hong Kong KMB</B>.<P>

This module is an extension of the amazing [MagicMirror<sup>2</sup>](https://github.com/MichMich/MagicMirror) project by [MichMich](https://github.com/MichMich/) which has inspired me to share my coding skills with others as well. Check it out, you know you want to :). <P>

It's always nice to see mirrors using my work, so feel free to send me some screenshots of your implementations.<P>

Lastly, why not join in on our discussions at the official [MagicMirror<sup>2</sup> Forum](http://forum.magicmirror.builders/)?

## Screenshots

![Chinese version](screenshots/screenshot_zh.png)
![English version](screenshots/screenshot_en.png)

## Current version

v1.0.0

## Languages
As of version 1.0.0, MMM-HK-KMB features language support for `Chinese (zh)` and `English (en)` mirrors.

## Prerequisite
A working installation of [MagicMirror<sup>2</sup>](https://github.com/MichMich/MagicMirror)
 
## Dependencies
  * npm
  * [request](https://www.npmjs.com/package/request)
  * [node-schedule](https://www.npmjs.com/package/node-schedule)

## Installation
1. Navigate into your MagicMirror's `modules` folder.
2. Execute `git clone https://github.com/winstonma/MMM-HK-KMB.git`.
3. Execute `cd MMM-HK-KMB`.
3. Execute `npm install`.

## Module behavior
Please note that this module auto-creates a module header which displays the name of the chosen Hong Kong local transport stop. It is therefore recommended not to add a 'header' entry to your config.js for this module.<P>
This module automatically disappears from your mirror as soon as a station has stopped offering connections at night. It reappears as soon as your chosen station is scheduled to be served again.<P>
This module has been programmed to allow for multiple instances. Simply add more MMM-HK-KMB config entries to your config.js file to display multiple stations and configure them according to your needs.

## Configuration
Sample minimum configuration entry for your `~/MagicMirror/config/config.js`:

    ...
    
    {
        module: 'MMM-HK-KMB',
        position: 'top_left',
        config: {
            stops: [
                {
                    stopID: 'HO06-S-1250-0',		// Which stop would you like to have displayed?	
                }
            ]
        }
    } 						// If this isn't your last module, add a comma after the bracket
    
    ...

Sample configuration entry for your `~/MagicMirror/config/config.js` with optional parameters:

    ...
    
    {
        module: 'MMM-HK-KMB',
        position: 'top_left',
        config: {
            stops: [
                {
                    stopID: 'HO06-S-1250-0',		// Which stop would you like to have displayed?	
                }
            ],
            labelRow: true, // Show or hide column headers
            reload: 60000 	// How often should the information be updated? (In milliseconds)
        }
    } 						// If this isn't your last module, add a comma after the bracket
    
    ...

## Figuring out the correct stopID
1. Open your web browser and navigate to the [KMB Mobile Page](http://m.kmb.hk/tc/).
2. Use the top search field to find the Line that the stop will stopped.
3. Once you can see the stop in your browser, click the Map.
4. When a new page is being displayed, check the link (e.g. http://www.kmb.hk/chi/map.php?file=HO06-S-1250-0). Note the last portion of the link (e.g. HO06-S-1250-0)is the `StopID` you are looking for.

## Config Options
| **Option** | **Default** | **Description** |
| :---: | :---: | --- |
| stopID | HO06-S-1250-0 | <BR>Which stop would you like to have displayed? <BR><EM> Default: HO06-S-1250-0</EM><P> |
| stopName | Stop | <BR>How would you want the stop name be displayed? <BR><EM> Default: Stop</EM><P> |
| labelRow<BR>`optional` | true | <BR> Show or hide column headers<BR> <EM>Possible values: true, false</EM><P> |
| reload<BR>`optional`  | 60000 | <BR> How often should the information be updated? (In milliseconds) <BR><EM> Default: Every minute </EM><P> |

## Licence
MIT License

Copyright (c) 2016 Winston (https://github.com/winstonma/)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
