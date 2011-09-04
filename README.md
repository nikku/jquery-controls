jQuery controls
===============

Small [jQuery](http://jquery.com/) plugin which allows other jQuery plugins to 
register custom click controls on page elements.

Features
--------

* Offers `$.fn.controls.bindings` as an entry point for other jQuery plugins to add custom click controls

Requirements
------------

* [jQuery](http://jquery.com/) (tested with jQuery >= 1.4.2 but might work with earlier versions)

Usage
-----

Include requirements and plugin in the header of your website

```html
<html>
    <head>
        <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
        <script type="text/javascript" src="jquery.controls.js"></script>
    </head>
    <!-- ... -->
```

Register controls for a certain element, e.g. a link with `.ajax` as class

```html
<script type="text/javascript">
    $.extend($.fn.controls.bindings, {
        "a.ajax": function(event) {
            alert("Won't trigger original click: Is an AJAX link!");
            event.preventDefault();
        }
    });
</script>
```

Execute `.controls()` on an element to bind all matching triggers to it

```html
<script type="text/javascript">
    // Wait for page load
    $(function() {
        // Bind to document
        $(document).controls();
    });
</script>
```