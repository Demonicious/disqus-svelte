### Disqus-Svelte
This is a package of pre-made components used to intergrate [Disqus](https://disqus.com/) services into your Svelte Applications.

#### 1. Installation:
You can install using [npm](https://npmjs.com) as such:
```
npm i -D disqus-svelte
```

#### 2. Usage:
```html
<script>
	import Comments from "disqus-svelte"; // You can use any alias.
</script>

<Comments identifier="my-blog-post-41" />
```
##### Available Props:
* **Required** `identifier` : The unique identifier of the page. The component will work without assigning this & throw a warning instead, but It's not guaranteed to always work.
* **Optional** `url` : The complete URL of the page. *Default: window.location.href*.
* **Optional** `container` : The class name of the Disqus  Comments Thread container..

#### 3. Comment Count:
##### Setup:
```html
<!-- The Root App file (App.svelte) -->
<script>
	import { Count } from "disqus-svelte";
</script>

<Count shortname="your-disqus-site-shortname" />
```
##### Using Comment Count:
```html
<!-- Append `#disqus_thread` to the `href` attribute in your links.
This will tell Disqus which links to look up and return the comment count. 

For example: -->
<a href="http://foo.com/bar.html#disqus_thread">Link</a>`.
```
##### Available Props:
**Required** `shortname` : The Shortname of your site provided by Disqus.

**[GitHub](https://github.com/demonicious/disqus-svelte)**