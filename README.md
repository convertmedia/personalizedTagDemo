# Personalized Tag Demo 

## Getting Started
place the tag script in the page 
```js
 <!-- BEGIN CONVERTMEDIA JS TAG -->
 <SCRIPT type="text/javascript" SRC="//15.basebanner.com/BidRHanSer?oid=15&width=2&height=2&pubid=PUBLISHER_ID&tagid=TAG_ID&pstn=ENTER_PLACEMENT_ID_HERE&noaop=1&revmod=INSERT_CONTENT_TYPE&encoded=1&cb=INSERT_CACHEBUSTER&keywords=INSERT_COMMA_SEPARATED_KEYWORDS&callback=document.write&urlonly=1"></SCRIPT>
```

## Personalization how to:
```js
<script>
        window.cmTagConfig = {
            isDebug: true,
           // onOutOfView: "none",
            vertical: "mizi",
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
