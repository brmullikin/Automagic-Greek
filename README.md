# Greek Automagically

## What it Does and Why

Greek Automagically uses the natural font-stack priority within a browser to render polytonic Greek from a specified Greek font file, without altering the font used for English characters (and character sets).

The idea behind Automagic Greek is simple: use the natural font-stack priority in a web browser to apply a separate font to any polytonic Greek within the document, without altering the font used for English characters (and other character sets).

Automagic Greek works by loading a modified Greek font which contains only the polytonic Greek characters (Or any other characters which you wish replaced). This is useful, for example, if the font which you wish to use for English text has unsuitable polytonic Greek characters, but you either can't, or don't want to apply a styling class around each occurrence of Greek. 

    English Text τῇ τῶν Ἑλληνικῶν γραφῇ

vs.

    English Text <span class="greek">τῇ τῶν Ἑλληνικῶν γραφῇ</span>

Presumably you could collapse the font-files, such that you include the Greek font within the English font of your choice, but that is undesirably because it lacks portability: what if you wish to change the English font-stack? It seemed the better solution to separate the files.

## Instructions

Simply upload the modifed font files to your webserver and link to them using @font-face like such:

    @font-face {
    font-family: 'GFS Porson';
    src: url('path/to/porson/gfsporson-regular.eot');
    src: local('GFS Porson'), 
		 url('path/to/porson/gfsporson-regular.eot?#iefix') format('embedded-opentype'),
		 url('path/to/porson/gfsporson-regular.woff') format('woff'), 
		 url('path/to/porson/gfsporson-regular.ttf') format('truetype'), 
		 url('path/to/porson/gfsporson-regular.svg#gfs_porsonregular') format('svg');
    font-weight: normal;
    font-style: normal;
    }

then make sure to give priority to the font in your css:

    font-family: "GFS Porson", "other", "fonts", "here", serif;

I recommend applying this to a high level tag, such as the ```<body>``` tag.

## What's Included

1. The original GFS Porson file from the [Greek Font Society](http://www.greekfontsociety.gr) along with the appropriate license files and specimen pdf
2. The (slightly) modified GFS Porson
	* @font-face files generated by [Font Squirrel](http://www.fontsquirrel.com/)
	* Example css and html use

## For the future

1. Modify and include more Greek fonts