<h1 class="capitalize">COMD2451</h1>
<h2 class="capitalize center">CSS Media Queries and Responsive Web Design</h2>

---

<section class="section">
    <h2 class="sentence">So what IS Responsive Web Design?</h2>

***Responsive*** `web design` ***makes*** your `web page` ***look good*** on ***all devices***.

***Responsive*** `web design` uses ***only*** `HTML` and `CSS`.
</section>

---

<section class="section">
    <h2 class="sentence">Designing the best experience for everyone</h2>

***Regarding*** `web design` for ***everyone***, `w3schools` ***states***:

> Web pages can be viewed using many different devices: desktops, tablets, and phones. Your web page should look good, and be easy to use, regardless of the device.

> Web pages should not leave out information to fit smaller devices, but rather adapt its content to fit any device.

> It is called responsive web design when you use CSS and HTML to resize, hide, shrink, enlarge, or move the content to make it look good on any screen.

<aside>
    Note: take the students to the [Responsive Web Design - Introduction](https://www.w3schools.com/css/css_rwd_intro.asp) page on w3schools to show examples of responsive design on various devices. And there is a great example of use of the universal selector and box-sizing: border-box in the Chania responsive web site example.
</aside>

</section>

---

<section class="section">
    <h2 class="sentence">So what IS a CSS media query?</h2>

A `CSS media query` is a `CSS technique` ***introduced*** in `CSS3`. It ***uses*** the `@media rule` to ***include*** a ***block*** of `CSS properties` ***only*** if a ***certain condition*** is ***true***.

</section>

---

<section class="section">
    <h2 class="sentence">The CSS media query and our basic site navigation</h2>

We are ***going*** to be ***using*** the `CSS media query` in ***two places*** in our `portfolio site`. ***One*** is in the `site navigation`, and the ***other*** will be in our `CSS Grid columns` ***containing*** our `images` on our `portfolio page`. ***Other opportunities*** to ***use*** it ***might arise***, but ***those*** are the ***two*** `available opportunities` ***right now***.

In our `site navigation`, ***right now*** we have the ***following*** `CSS` for ***larger screens***:

The `CSS` (***including*** the `media query` for ***smaller screens***):

```css
* {
    padding: 0;
    margin: 0;
}

/* nav styles using Flexbox (screens greater than 899px) */

nav {
    width: 100vw;
	/* background: #D6EFFF; */
    background: #D6EFFF;
}

ul {
    display: flex;
    justify-content: flex-end;
}

li {
    list-style-type: none;
    margin: 2vw;
    font-size: 2.75vh;
}

a {
    text-decoration: none;
    color: black;
    padding: 2vw;
    font-family: monospace;
}

a:hover {
    color: #2f6690;
}

.hamburger {
    display: none;
}

/* End nav styles using Flexbox (screens greater than 899px) */

/* Logo Styling */
.header {
    margin-top: 2rem;
}

.header .logo {
    text-align: center;
    font-size: 1.75rem;
    text-decoration: none;
    background: #f79ece;
    width: 93.44px;
    height: 76px;
    padding: 1.25rem;
    vertical-align: bottom;
    margin-left: 1rem;
}

/* media query for site navigation */

@media (max-width: 899px) {
	ul {
		/* display: block; */
		flex-direction: column;
		margin-top: 5rem;
	}

	li {
		margin: 0 0 0 1.25rem;
	}

	a {
		display: block;
	}

	.header {
		margin-top: 0.75rem;
	}

	.header .logo {
		margin-left: 1.25rem;
	}

	/* Responsive Hamburger menu styling */
	.hamburger {
		display: block;
		position: absolute;
		/* always keep ham on top of everything */
		z-index: 1000;
		top: 20px;
		right: 20px;
		width: 36px;
		height: 36px;
		border: none;
		cursor: pointer;
		background-color: transparent;
		/* show the hamburger menu image */
		background-image: url("https://ljc-dev.github.io/testing0/ham.svg");
		background-size: 100%;
	}

	/* change hamburger image to close */
	.showClose {
		background-image: url("https://ljc-dev.github.io/testing0/ham-close.svg");
		background-size: 100%;
	}

	.navbar {
		position: absolute;
		top: 0;
		left: 0;
		background: #bc2732;
		width: 100vw;
		height: 100vh;
		overflow: hidden;
		color: white;
		/* hide the menu above the screen by default */
		transform: translateY(-100%);
		/* transition adds a little animation when sliding in and out the menu */
		transition: transform 0.2s ease;
	}

	.showNav {
		/* show the menu */
		transform: translateY(0);
	}
}
```

So if the `width` of the `viewport` is ***less than*** `< 900px`, or has a `max-width` of `899px`, then the `flex-direction` of the `nav` will ***no longer*** be `row`. It will be `column`. Which would ***render*** the same as the ***following*** `CSS code`:

```css
ul {
    display: block;
}
```

I ***chose*** a `max-width: 899px` because ***that*** is the `width` we ***need*** to **make sure** that ***all*** `navigation menu links` ***fit*** in the `viewport`. ***Any*** `width` ***less than*** `899px` would be ***too narrow***!

I **just thought** it would be ***cool*** to ***get*** to the ***same place*** a ***bit differently*** using `flex-direction: column;` ***instead of*** `display: block;`! And ***that*** is ***it***!  

***Hopefully*** we will **be able** to ***separate*** our `navigation concerns` ***from*** our `CSS Grid column concerns` in our ***responsive design*** (`done`).

</section>

---

<section class="section">
    <h2 class="sentence">The CSS media query and our CSS Grid image gallery</h2>

The ***next thing*** we **have** to ***make sure*** is that our ***vertically columned*** `image gallery` will ***render nicely*** in ***smaller screens***. Our ***goal*** is to make them ***display*** on `top` of `each other` (`one column`) in ***small screens*** such as an `iPhone 4`, for ***example***!

</section>

---

<section class="section">
    <h2 class="sentence">Adding a media query to our CSS Grid</h2>

The **CSS**:

```css
@media (max-width: 799px) {
    section {
        display: block;
        width: 97.5%;
        margin: 0 auto;
    }
}
```

This is ***all*** we ***need*** to do to ***make*** our `images` ***stack*** `one` on `top` of the `other` in ***smaller screens***.

</section>

---

<section class="section">
	<h2 class="sentence">So when is using media queries useful?</h2>

`Media queries` are ***useful*** when you want to ***modify*** your `site` or `app` ***depending*** on a ***device's*** `general media type` (***such as*** `print` vs `screen`), ***or*** ***specific characteristics*** and ***parameters*** (***such as*** `screen resolution` or `browser viewport width`).

We have been ***going by*** `browser viewport width` ***using*** the `max-width property`. ***Some*** go the ***other*** `way around`, and ***use*** the `min-width property`. ***Either way*** is `completely valid`.

***Using*** the `min-width` ***approach*** is ***also*** known as `"mobile first"`. That is ***because*** the `design` ***outside*** of the `media query` ***relates*** to `mobile design`. ***Only*** the `CSS` ***inside*** the `media query` ***relates*** to `desktop design`.

`CSS code` is ***considered*** `mobile first design` when we **use** the `min-width` ***CSS property*** in our `media query` and the ***specified width*** is that of `larger screens`, i.e. `min-width: 800px` or `min-width: 900px`, or even `min-width: 1280px`, etc. The `min-width` should be able to ***fit*** the `content` of the `page` on ***any width*** `larger` than the `min-width` ***provided*** without omitting ***any*** `page content`.

***Using*** the `max-width` ***approach*** is also ***technically known*** as `"desktop first"` (larger screens). That is ***because*** the `design` ***outside*** of the `media query` ***relates*** to the `desktop design`. ***Only*** the `CSS` ***inside*** the `media query` ***relates*** to the `mobile design`.

`CSS code` is ***considered*** to be `desktop first design` when we ***use*** the `max-width` ***CSS property*** in our `media query` and the ***specified width*** is that of `smaller screens`. i.e. `max-width: 899px`, `max-width: 599px`, etc. The `max-width` should be able to ***fit*** the `content` of the `page` in ***any width*** `smaller` or `equal` to the `max-width` provided ***without omitting*** any `page content`.

</section>

---

<section class="section">
	<h2 class="sentence">The media syntax</h2>

A `media query` ***consists*** of an ***optional*** `media type` and ***any number*** of `media feature expressions`. ***Multiple queries*** can be ***combined*** in ***various ways*** by ***using*** `logical operators`. `Media queries` are `case-insensitive`. But ***keep*** it ***simple*** anyway!

</section>

---

<section class="section">
	<h2 class="sentence">Media conditions</h2>

A `media query` ***computes*** to `true` when the `media type` (***if specified***) ***matches*** the `device` ***on which*** the `document` is ***being displayed*** and ***all*** `media feature expressions` ***compute*** to `true`.

`Queries` ***involving*** `unknown media types` ***always evaluate*** to `false`.

</section>

---

<section class="section">
	<h2 class="sentence">Media Types</h2>

`Media types` ***describe*** the `general category` of a `device`. ***Except*** for when ***using*** the `not` or `only` ***logical operators***, `media type` is ***optional*** and the ***all*** `type` is ***implied***.

For ***example***, we are `using`

```css
@media (max-width: 799px) {
	section {
        display: block;
        width: 97.5%;
        margin: 0 auto;
    }
}
```

***Here***, we do ***not*** `define` a ***specific*** `@media type`, so the `all type` is ***implied***. And we ***do want*** our `site` to ***render*** a `certain way` on ***all*** `devices`!

</section>

---

<section class="section">
    <h2 class="sentence">Logical Operators in Media Queries</h2>
    
According to [Shaye Howe](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/),

> Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including and, not, and only.

And 

> Using the and logical operator within a media query allows an extra condition to be added, making sure that a browser or device does both a, b, c, and so forth. Multiple individual media queries can be comma separated, acting as an unspoken or operator.

<aside class="notes">
    Note: Take the students to Shay Howe's [Responsive Web Design](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/) to show examples.
</aside>

</section>

---

<section class="section">
    <h2 class="sentence">The not logical operator and media types</h2>
    
A `not logical operator` can be ***used*** at the ***beginning*** of a `media query` to ***toggle*** the `truthiness` of the ***whole*** `query`.

The `not operator` is **useful** to ***apply*** `styles` when ***certain conditions*** are ***not met*** by the `browser` or `device`. In the ***following*** `example`, the `media query` ***will apply*** when the `primary pointing device` ***can’t hover*** over `elements`:

```css
@media not screen and (hover: hover) {
    p {
        font-weight: bold;
    }
}
```

This `example` can be ***viewed*** on the `article` entitled [CSS Media Queries: Quick Reference & Guide](https://www.digitalocean.com/community/tutorials/css-media-queries) on `Digital Ocean`. I just ***added*** the `CSS rule set` inside.


Going back to `Shay Howe`, ***another example*** of the `use` of the `not logical operator` with `media types` is the ***following***:

```css
@media not screen and (color) {
    h1 {
        text-align: center;
        font-size: 2.25rem;
    }
}
```

The ***above*** `expression` ***applies*** to any `device` that does ***not have*** a `color screen`. It ***applies*** to `black` and `white` or `monochrome screens`, for ***example***.

Regarding the `logical not operator`, ***according*** to [Digital Ocean,](https://www.digitalocean.com/community/tutorials/css-media-queries),

> Note that with not the media type is not optional. Also, not doesn’t negate an entire query list (queries separated with commas), but only one query.

</section>

---

<section class="section">
    <h2 class="sentence">The only logical operator and media types</h2>
    
The `only logical operator` is a ***bit special*** and `hides` the ***entire query*** in `older browsers`. `Older browsers` ***don't understand*** the `only keyword`, so the ***entire*** `media query` is ***ignored***.

Regarding the `logical only operator`, ***according*** to [Digital Ocean,](https://www.digitalocean.com/community/tutorials/css-media-queries),

> As with the not operator, the media type is not optional when using only. Note that legacy browsers that don’t support Media Queries level 3 are rare now so in most cases the use of only is unnecessary.

Regarding the `logical only operator`, ***according*** to
[Shay Howe](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/),

> The only logical operator is a new operator and is not recognized by user agents using the HTML4 algorithm, thus hiding the styles from devices or browsers that don’t support media queries. Below, the expression selects only screens in a portrait orientation that have a user agent capable of rending media queries.

He ***did write*** his ***book*** way back in 2014. ***A lot*** has ***changed*** with `browsers` (***and*** `media queries`) since then!

According to `MDN` on ***their page*** entitled [Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries), as regards the `logical only operator `(now),

> The only operator is used to apply a style only if an entire query matches, and is useful for preventing older browsers from applying selected styles. When not using only, older browsers would interpret the query screen and (max-width: 500px) as screen, ignoring the remainder of the query, and applying its styles on all screens. If you use the only operator, you must also specify a media type.

We are `keeping things simple` on our `portfolio site`. Complexity is ***not necessary*** for our setup. It is ***always*** `best practice` to `keep things` as **simple** as ***possible***, and only ***add features*** if they are ***necessary***!

</section>

---

<section class="section">
	<h2 class="sentence">Available media types</h2>

+ `all`: ***suitable*** for ***all*** `devices`.

+ `print`: ***Intended*** for `paged material` and `documents` ***viewed*** on a `screen` in `print preview mode`. (Please ***see*** [paged media](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media) for ***information about*** `formatting issues` that are ***specific*** to ***these formats***.)

+ `screen`: ***Intended primarily*** for `screens`.

+ `speech`: ***Intended*** for `speech synthesizers`.

</section>

---

<section class="section">
	<h2 class="sentence">Media Features</h2>

`Media features` ***describe*** `specific characteristics` of the `user agent`, `output device`, or `environment`. `Media feature expressions` ***test*** for ***their*** `presence` or `value`, and are ***entirely optional***. ***Each*** `media feature expression` ***must*** be ***surrounded*** by `parentheses`.

</section>

---

<section class="section">
	<h2 class="sentence">Available media features</h2>

+ `any-hover`: Does ***any*** `available input mechanism` ***allow*** the `user` to ***hover over*** `elements`? (***added*** in `Media Queries Level 4`).

+ `any-pointer`: Is ***any*** `available input mechanism` a `pointing device`, and ***if so***, ***how accurate*** is it? (***added*** in `Media Queries Level 4`).

+ `aspect-ratio`: The `ratio` ***between*** the `width` and the `height` of the `viewport`.

+ `color`: The `number` of `bits` ***per*** `color component` for the `output device`.

+ `color-gamut`: The ***approximate*** `range` of `colors` that are ***supported*** by the `user agent` and `output device` (***added*** in `Media Queries Level 4`).

+ `color-index`: The ***number*** of `colors` the `device` can ***display***.

+ `grid`: ***Whether*** the `device` is a `grid` or `bitmap`.

+ `height`: The `viewport height`.

+ `hover`: ***Does*** the `primary input mechanism` ***allow*** the `user` to ***hover over*** `elements`? (***added*** in `Media Queries Level 4`).

+ `inverted-colors`: Is the `browser` or ***underlying*** `OS` ***inverting*** `colors`? (***added*** in `Media Queries Level 4`).

+ `light-level`: ***Current*** `ambient light level` (***added*** in `Media Queries Level 4`)

+ `max-aspect-ratio`: The `maximum ratio` ***between*** the `width` and the `height` of the `display area`

+ `max-color`: The `maximum number` of `bits` ***per*** `color component` for the `output device`.

+ `max-color-index`: The `maximum number` of `colors` the `device` can ***display***.

+ `max-height`: The `maximum height` of the `display area`, such as a` browser window`.

+ `max-monochrome`: The `maximum number` of `bits` ***per*** ``"color"`` on a `monochrome` (`greyscale`) `device`.

+ `max-resolution`: The `maximum resolution` of the `device`, ***using*** `dpi` or `dpcm`.

+ `max-width`: The `maximum width` of the `display area`, ***such as*** a `browser window`.

+ `min-aspect-ratio`: The `minimum ratio` ***between*** the `width` and the `height` of the `display area`.

+ `min-color`: The `minimum number` of `bits` ***per*** `color component` for the `output device`.

+ `min-color-index`: The `minimum number` of `colors` the `device` can ***display***.

+ `min-height`: The `minimum height` of the `display area`, ***such as*** a `browser window`.

+ `min-monochrome`: The `minimum number` of `bits` per ``"color"`` on a `monochrome` (`greyscale`) `device`.

+ `min-resolution`: The `minimum resolution` of the `device`, ***using*** `dpi` or `dpcm`.

+ `min-width`: The `minimum width` of the `display area`, ***such as*** a `browser window`.

+ `monochrome`: The `number` of `bits` ***per*** `"color"` on a `monochrome` (`greyscale`) `device`.

+ `orientation`: The `orientation` of the `viewport` (`landscape` or `portrait mode`).

+ `overflow-block`: ***How does*** the `output device` ***handle content*** that ***overflows*** the `viewport` ***along*** the `block axis` (***added*** in `Media Queries Level 4`).

+ `overflow-inline`: Can `content` that ***overflows*** the `viewport` ***along*** the `inline axis` be `scrolled` (***added*** in `Media Queries Level 4`).

+ `pointer`: Is the `primary input mechanism` a `pointing device`, and ***if so***, ***how accurate*** is it? (***added*** in `Media Queries Level 4`).

+ `resolution`: The `resolution` of the `output device`, ***using*** `dpi` or `dpcm`.

+ `scan`: The `scanning process` of the `output device`.

+ `scripting`: Is `scripting` (e.g. `JavaScript`) ***available***? (***added*** in `Media Queries Level 4`).

+ `update`: ***How quickly*** `can` the `output device` ***modify*** the `appearance` of the `content` (***added*** in `Media Queries Level 4`).

+ `width`: The `viewport width`.

<aside>
	Note: visit the [CSS @media Rule](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp) on w3schools to show some very good examples using various media features.
</aside>

</section>

---

<section class="section">
    <h2 class="sentence">Related Resources</h2>

+ [A Complete Guide to CSS Media Queries: CSS Tricks](https://css-tricks.com/a-complete-guide-to-css-media-queries/)

+ [Responsive Web Design - Media Queries: w3schools](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)

+ [CSS @media Rule: w3schools](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)

+ [@media: MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)

+ [Using media queries: MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

+ [CSS Media Queries: Quick Reference & Guide](https://www.digitalocean.com/community/tutorials/css-media-queries)

+ [Responsive Web Design](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/)

</section>
