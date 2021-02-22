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

The `CSS` (***including*** the `media query`):

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

I **just thought** it would be ***cool*** to ***get*** to the ***same place*** a ***bit differently***! And ***that*** is ***it***!  

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

This is ***all*** we ***need*** to do to ***make*** our `images` ***stack*** `one` on `top` of the `other`.

If ***any*** of you ***decide*** to have ***more than*** `3 columns` (or ***less than*** `3 columns`) in your `image gallery`, the `media query CSS code` ***might*** differ ***slightly***. If ***that*** is the ***case***, let me ***know*** and I can go over ***individual cases*** `one-on-one`.

</section>

---

<section class="section">
	<h2 class="sentence">So when is using media queries useful?</h2>

`Media queries` are ***useful*** when you want to ***modify*** your `site` or `app` ***depending*** on a ***device's*** `general type` (***such as*** `print` vs `screen`), ***or*** ***specific characteristics*** and ***parameters*** (***such as*** `screen resolution` or `browser viewport width`).

We have been ***going by*** `browser viewport width` ***using*** the `max-width property`. ***Some*** go the ***other*** `way around`, and ***use*** the `min-width property`. ***Either way*** is `completely valid`.

***Using*** the `min-width` ***approach*** is ***also*** known as ``"mobile first"``. If ***that*** is the ***way*** you ***want*** to ***go***, you could always ***refactor*** your `CSS` and ***make it*** a `"mobile first"` ***design***!

</section>

---

<section class="section">
	<h2 class="sentence">The media syntax</h2>

A `media query` is ***composed*** of an ***optional*** `media type` and ***any number*** of `media feature expressions`. ***Multiple queries*** can be ***combined*** in ***various ways*** by ***using*** `logical operators`. `Media queries` are `case-insensitive`. But ***keep*** it ***simple*** anyway!

</section>

---

<section class="section">
	<h2 class="sentence">Media conditions</h2>

A `media query` ***computes*** to `true` when the `media type` (***if specified***) ***matches*** the `device` ***on which*** the `document` is ***being displayed*** and ***all*** `media feature expressions` ***compute*** to `true`.

`Queries` ***involving*** `unknown media types` are ***always*** `false`.

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
	<h2 class="sentence">Media features</h2>

+ 1any-hover1: Does ***any*** `available input mechanism` ***allow*** the `user` to ***hover over*** `elements`? (***added*** in `Media Queries Level 4`).

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

</section>
