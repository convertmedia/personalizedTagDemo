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
#### isDebug
accepts: true/false

#### onOutOfView
accepts: "none","pause","detach"

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
