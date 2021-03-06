JQuery Timeline
========

Usage
-----
            $("#tline").syrinxTimeline({
                bands: [
                {
                    width: "10%",
                    intervalUnit: Timeline.DateTime.DECADE,
                    intervalPixels: 200,
                    date: d,
                    showEventText: false,
                    theme: theme,
                    highlight: false,
                    decorators: [
                        new Timeline.SpanHighlightDecorator({
                            startDate: "Nov 14 1840 00:00:00 GMT",
                            endDate: "Dec 05 1926 00:00:00 GMT",
                            startLabel: "birth",
                            endLabel: "death",
                            color: "#FFC080",
                            opacity: 50,
                            theme: theme
                        })
                    ],
                    etherPainter: new Timeline.YearCountEtherPainter({
                        startDate: "Nov 14 1840 00:00:00 GMT",
                        multiple: 5,
                        theme: theme
                    })
                },
                {
                    width: "90%",
                    intervalUnit: Timeline.DateTime.DECADE,
                    intervalPixels: 200,
                    eventSource: eventSource,
                    date: d,
                    theme: theme,
                    layout: 'compact'
                }]
            });


Overview
--------

This is the [Simile timeline](http://www.simile-widgets.org/timeline/) gone through an overhaul to fix lots of longstanding bugs, remove code not being used, and streamline needed code to use jQuery which reduces the existing code in size.  

I've created this repository to hold my work without having to deal with the original goals of timeline and integration with their larger collection of tools such as [Exhibit3](http://www.simile-widgets.org/exhibit3/).
These goals are stated below.

The JavaScript for the timeline is contained within the [Timeline3/jquery.timeline](http://github.com/kusog/timeline/tree/master/Timeline3/jquery.timeline) folder.  The overall project is included within a Visual Studio 2012 ASP.NET MVC project, which acts as a test environment.
The JavaScript in the jquery.time folder has no dependencies on anything .NET.

Goals
-----

* Reduce total bytes downloaded to browser in order to provide timeline plugin.
* Change loading process to just using one css file and one js file that are included in the page like other mainstream jquery plugins.
* Remove all code that is just replicating something from jQuery and use jQuery directly.
* Change timeline into a real jQuery plugin that is configured and used like other mainstream jQuery plugins.
* Model the way widgets are created in jQuery UI, but not require jQuery UI in order to be used.  The only dependency is jQuery.
* Change code that could be rewritten to use jQuery to use jQuery when the results will be reduction of code size and increased conformity to standard jQuery coding practices.
* Remove all dead code, or code that is secondary to mainstream usage.  Secondary features should be added via plugins on top of the main timeline codebase.
* Solid tablet and phone support.


Examples
--------

There is currently just one example, the life time of the artist Monet, which is just an updated version of the [original Simile timeline example](http://www.simile-widgets.org/timeline/examples/monet/monet.html).
The monet example also contains the [combined and minified version of the timeline](http://github.com/kusog/timeline/tree/master/Examples/Monet/timeline) css and js, which can easily be lifted and reused in your own projects.

You can see the monet example live at http://timeline.kusog.org