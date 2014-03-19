# Cartidge Module Documentation (FoodNetwork)
<small>Updated 08/06/2013</small>

## Description ##
A cartidge is a simple module that can run on many FoodNetwork.com and Food.com pages. The module is inserted into the page's **\#sponsorCtr1** div via Javascript. The assets are provided in an Excel document and will contain all info needed. There are not any other asset files.

![*Foodnetwork.com Cartidge Module*](http://www.scrippsonline.com/vendors/docs/cartridge/screenshot.jpg "Food Network Cartridge")

## Production Overview ##
Production is very simple and involves a single creative file. The process involves creating the HTML markup and then storing that HTML as an escaped JS string. The JS then appends the contents to the sponsorCtr1 div. The attached template file contains both the JS and HTML to speed up creation. The HTML structure is at the bottom. This will NOT be included in the final creative. The top section contains the actual creative that will be setup in Mockingbird and trafficked.

### Standard Process
- Update HTML portion of template with Excel values.
- Convert HTML portion to an escaped JS string.
- Set syncedContent variable in top section to the HTML string.
    - I use [http://accessify.com/tools-and-wizards/developer-tools/html-javascript-convertor/](http://accessify.com/tools-and-wizards/developer-tools/html-javascript-convertor/) to make this fast. Choose 3rd option to "Build up a string variable that you can use later". You can also manually escape the string or if you have a better method use that. It just needs to be valid JS.
- <del>Setup page locking. (Restrict module to a single page regardless of where it is trafficked)
    - You may hear this referred to as the "Sniffer-Stacker" by the coordinator because it allows us to stack this with other creatives and have it only run on a specific page.
    - To set this up, you need to grab the UniqueID of the page the module will run on (The URL will be in the Excel doc). You can get the unique ID by looking at the target page source or running `mdManager.getUniqueId()` within the JS console on the page.
    - Set the lockPageUid variable to value from previous step</del> **Page locking is deprecated. Ignore this**
    - In the template file, there are 2 if blocks. If not using the page lock, use the one that just checks for the `#myIDElement` and comment out or remove the other.
- At this point, the creative is complete and can be setup for preview in Mockingbird.
    - This are setup in the RSI project as well (PID 238). 
    - Use the followinw naming convention. `Sponsor Name Cartridge [Site] Month Year`
        - Example: `Ball Canning Cartridge [FN] July 2013`
    - Set Page Scrape URL to the target page provide in the Excel document
    - Put the creative in the Bigbox field under "Creative" and set the name to "Cartidge"
    - Provide preview link for review just like the RSIs.
    - The Mockingbird item is the only deliverable for these. There are no files to put up or send.
- See the included example.html for an example of a final version that was trafficked. You may also, look search the project 238 page in Mockingbird for "Cartridge" for more examples.

