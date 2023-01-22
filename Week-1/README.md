Web browser are most used software The main function of a browser is to present the web resource you choose, by requesting it from the server and displaying it in the browser window.The resource can be HTML document or PDF , location is URI (Uniform Resource Identifier)
It is intercepted by HTML and  CSS specifications .

Browser has user interfaces like :

.Address bar for inserting a URI
.Back and forward buttons
.Bookmarking options
.Refresh and stop buttons for refreshing or stopping the loading of current documents
.Home button that takes you to your home page

High level structure
1.User Interface : it includes address bar,back/forward button , bookmarking menu etc.
2.Browser engine : marshals actions between UI and rendering engine
3.Rendering engine : responsible for displaying requested content
4.Networking : network calls such as HTTP requests ,using different implementations for different platforms
5.UI back-end : used for drawing basic widgets like combo boxes and windows . This back-end exposes a generic  interface that is not platform-specific 
6.JS interpreter : used to parse and execute Javascript code.
7.Data Storage : this is a persistence layer. The browser may need to save all sorts of data locally such as cookies .






The RENDERING Engines

It displays requested contents on the  browser screen. It can only render HTML , XML and images in default state however other types can be rendered using plug-in .

Working of rendering engines 


The networking layer provides the rendering engine with the required documents .It parses the HTML document and convert elements to DOM nodes in a ‘content tree’ also parses style and data . Styling and visual instructions are used to create ‘render tree’.After this comes the layout process in which the each rectangle is given the exact co-ordinates where it should appear on the screen. After the layout operation is the paint operation in which whole of the render tree is traversed and the elements are drawn on the browser window using the UI back-end layer. This whole process does not take place one by one but takes place simultaneously



Layout

When the renderer is created and added to the tree, it does not have a position and size. Calculating these values is called layout or reflow. HTML uses a flow based layout model, it means that it is possible to compute the geometry of the layout in just one single pass. Elements later in the flow typically do affect the layout of the elements earlier in the flow. However this is not true for tables as they require more than one pass.



Painting

The render tree is traversed and the renderer’s ‘paint()’ method is called which paints the layout on the screen.
Painting is of two types : global and incremental. In incremental painting some of the renderers can change in a way that it does not affect the other renderers. If the renderer invalidates it’s rectangle on the screen, the OS marks it as a dirty region and generates a paint event.
The browsers are programmed to do minimum possible actions in response to a change.