_[Demo and API docs](http://leogr.github.io/iron-ajax-page/)_


##&lt;iron-ajax-page&gt;

An element that grabs html from your server via ajax and replace its content. Inspired by [pjax](http://pjax.herokuapp.com/).
> Currently, this is just a proof of concept element. 

### Features

In its typical usage with `iron-location` for pushState, it can deliver a fast browsing experience
with real permalinks and a working back button:
```html
<iron-location path="{{path}}"></iron-location>
<iron-ajax-page src="[[path]]" loaded>
    Initial content
</iron-ajax-page>
```
The element performs a request whenever its `src` property is changed.

With `loaded` set to `true`, the element assumes that the server sent the initial content already
so it skips the first loading.
You can trigger a request explicitly by calling `generateRequest` on the element.

The example above assumes your server has been configured to look for `iron-ajax-page`'s requests
and can send back the specific content.
By default, an `X-Iron-Ajax-Page` header is attached to the generated request.
Requests can be customized by `headers`, `params`, and `url-rewrite-*` properties.

Furthermore, the element will force a full reload of the page if it receives an error or an empty response,
assuming that the server's response hasn't been properly configured.

