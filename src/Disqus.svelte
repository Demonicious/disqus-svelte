<script>
    import { onMount } from "svelte";
    
    export let url = window.location.href;
    export let container = "disqus_container";
    export let identifier;

    onMount(() => {
        if(url && identifier) {
            const config = document.createElement('script');
            config.type = 'text/javascript';
            config.innerHTML = 
            `const disqus_config = function () {
                this.page.url = '${url}';
                this.page.identifier = '${identifier}';
            };`;
            document.head.appendChild(config);

            const disqus = document.createElement('script');
            disqus.src = 'https://svelte-test.disqus.com/embed.js';
            disqus.setAttribute('data-timestamp', +new Date());
            (document.head || document.body).appendChild(disqus);
        } else console.error("In-sufficient Props for disqus-svelte Comments.\n\n The 'identifier' property containing a Unique Identifier for the current page is Required!");
    });
</script>

<div class={container}>
    <div id="disqus_thread"></div>
</div>