# Flourish scrollies

- https://help.flourish.studio/article/330-how-to-use-scrollytelling
- https://help.flourish.studio/article/485-how-to-customize-your-scrolly-configuration

## Things needed

### 1) Scripts

You can use story embeds or iframes. If you're using embeds you need the embed script in the head:

```html
<!-- We only need the embed script once (and if we're using embeds): -->
<script src="https://public.flourish.studio/resources/embed.js"></script>
```

Secondly you'd need the flourish scrolly lib:

```html
<!-- Add the Flourish Scrolly library -->
<script src="https://cdn.flourish.rocks/flourish-scrolly-v3.1.0.min.js"></script>
```

### 2) the HTML

Next you need a wrapper div wrapping up:

- the embed or the iframe of the published story
- the elements that control the visual:

```html
<!-- This is a wrapper around the scrolly in case you want to apply extra styling (see Step 6 in the help doc) -->
<div id="my-wrapper-1" class="wrapper">
  <!--  Drop your choice of Flourish embed code - you can use either the script or iframe embed codes here -->
  <div
    class="flourish-embed"
    data-src="story/1664174?932"
    data-url="https://flo.uri.sh/story/1664174/embed"
    data-height="100vh"
  ></div>

  <!-- Here is where you add your captions, linking them to specific slides in the story -->
  <p>Text for slide 1<a href="#story/1664174/slide-1"></a></p>
  <p>Text for slide 2<a href="#story/1664174/slide-2"></a></p>
</div>
```

The `data-height="100vh"` is the space the visualisation takes (which will always be centered by default). The embed/iframe wrapper (`.fl-scrolly-section`) will always be as high as the visualisation plus all the text elements. With many text elements the overall height can be quite large...

### 3) The init call

Finally, you need to initialise the library

```html
<!-- Initialize the library to turn your story into scrolly magic! -->
<script type="text/javascript">
  initFlourishScrolly();
</script>
```

You can add a configuration object to the init function (see [here](https://help.flourish.studio/article/485-how-to-customize-your-scrolly-configuration?preview=622b2a4cab585b230a89f8f5)).

---

**Note, you need (1) and (3) only once for multiple visualisations (and you need (1) only when using embeds).**
