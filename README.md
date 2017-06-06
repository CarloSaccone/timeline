# Timeline.js

This is a fork of the timeline.js Raphaeljs' plugin by mquan (https://github.com/mquan/timeline).

Actual implementation adds:

* support to multidimensional datasets (=> more timeline rows on the same chart)
* support to color customization (data-driven) for events and bars
* improved timescale visual helpers (added vertical lines for "Now" and timescale steps)
* save chart as image (credits to: http://bl.ocks.org/battlehorse/1333906)

## Output

![demo](https://github.com/CarloSaccone/timeline/blob/master/img/timeline.png)

## Usage

```
<div id="timeline"></div>
<script type="text/javascript">
	var todos = [{ name: 'idea formation', date: '2017-4-1', task: '', color:c.gray },
					{ name: 'Raphael plugin', date: '2017-4-10', task: '', color: c.blue },
					{ name: 'coding', date: '2017-4-30', task: '', color: c.green, marker: '\uf1e5', marker_fill: c.green },
					{ name: 'first release', date: '2017-5-7', task: '', color: c.red, marker: '\uf071', marker_fill: c.red }
		];

        var todos2 = [{ name: 'idea', date: '2017-1-28', task: '', color: c.gray },
					{ name: 'Raphael plugin', date: '2017-4-29', task: '', color: c.blue },
					{ name: 'coding', date: '2017-5-30', task: '', color: c.yellow },
					{ name: 'first release', date: '2017-7-2', task: '', color: c.black }
		];
        var todos3 = [{ name: 'xyz', date: '2017-3-28', task: '', color: c.gray },
					{ name: 'Raphael plugin', date: '2017-4-29', task: '', color: c.green },
					{ name: 'coding', date: '2017-5-30', task: '', color: c.yellow },
					{ name: 'first release', date: '2017-7-2', task: '', color: c.red }
		];
        
        var d1 = { lineInfo: "Activity #1", events: todos }
        var d2 = { lineInfo: "Activity #2", events: todos2 }
        var d3 = { lineInfo: "Activity #3", events: todos3 }

        document.addEventListener('DOMContentLoaded', function () {
            console.log("load");
            var dataset = [d1, d2, d3];

            var p1 = Raphael('timeline1');
            p1.timeline.draw(
                { dataset: dataset}, //data + settings
                //callback
                function (event) {
                    console.log(event)
                }
            );

        }, false);
</script>
```

## References

* Jquery
* RaphaelJS
* fontawesome (for graphic markers)
* canvg.js (for save as image features)