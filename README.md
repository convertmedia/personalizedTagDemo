# Personalized Tag Demo 

## Getting Started
1. Replace the query string keys
2. Place the tag script in the page 
```js
 <!-- BEGIN CONVERTMEDIA JS TAG -->
 <SCRIPT type="text/javascript" SRC="//15.basebanner.com/BidRHanSer?oid=15&width=2&height=2&pubid=INSERT_PUBLISHER_ID&tagid=INSERT_TAG_ID&pstn=ENTER_PLACEMENT_ID_HERE&noaop=1&revmod=INSERT_CONTENT_TYPE&encoded=1&cb=INSERT_CACHEBUSTER&keywords=INSERT_COMMA_SEPARATED_KEYWORDS&callback=document.write&urlonly=1"></SCRIPT>
```

## Tag Personalization
add personalization confif script to the page
```js
<script>
        window.cmTagConfig = {
            isDebug: true,
            onOutOfView: "detach"
        };
</script>
```
### Options

#### unitType
accepts: "INLINE"/"INTERSTITIAL"/"SLIDER"

#### isDebug
accepts: true/false


#### closeButton
**hasCloseButton**

accepts: true/fale

**secondsToCloseButton**

accepts: number 0...60

### Options For Inline Unit Only
#### onOutOfView
accepts: "none","pause","detach"

#### viewPercent
accepts: numbers 0...100

#### parentSelector
accepts: js/css selector/ array of js/css selectors
 default: no selector (the video will open next to the tag placement)
```js
//one selector
window.cmTagConfig = {
   parentSelectr:"div.block.B3 > div:nth-child(1)"
}
//array of selectors
window.cmTagConfig = {
   parentSelectr:["article","#div1","div.block.B3 > div:nth-child(1)"]
}
```

### Options For Interstital Unit Only
#### onClose
accepts:"detach"/"none"
default value:"none"

#### secondsToAd
accepts: number 0...60
default value:3

#### width
accepts: number 500...1000
default:9000

### Options For Slider Unit Only
#### secondsToAd
accepts: number 0...60
default value:3

#### width
accepts: number 300...1000
default:402

#### position
**horizontal**

accepts:"right"/"left"
default:"right"

**vertical**

accepts: "top"/"middle"/"bottom"
defautl: "bottom"

### Upcoming Options (next release features)
#### onReady
accepts: callback
```js
window.cmTagConfig = {
   onReady:function(){
     console.log("the adUnit is ready");
   }
}
```
#### onConversion
accepts: callback
```js
window.cmTagConfig = {
   onConversion:function(){
     console.log("the adUnit is playing the video ad");
   }
}
```
#### onAdDone
accepts: callback
```js
window.cmTagConfig = {
   onAdDone:function(){
     console.log("the adUnit is playing done playing the video ad ");
   }
}
```
#### onClosedByUser
accepts: callback
```js
window.cmTagConfig = {
   onClosedByUser:function(){
     console.log("the user closed clicked on the close button");
   }
}
```


### Example
```js
<script>
        window.cmTagConfig = {
            isDebug: true,
            onOutOfView: "detach",
            demandConfig: {
                waterfall: {
                    "totalTimeout": 180,
                    "tags": [
                        {
                            pixel:"http://localhost/pixel",
                            "url": "http://ad4.liverail.com/?LR_PUBLISHER_ID=151025&LR_SCHEMA=vast2-vpaid&LR_TITLE=%%title%%&LR_VIDEO_ID=%%video-url%%&LR_DURATION=30&LR_AUTOPLAY=1&LR_MUTED=0&LR_VERTICALS=%%VERTICAL%%&LR_TAGS=%%tag%%&LR_URL=%%domain%%"
                        }
                    ]
                }
            }
        };
    </script>
```
