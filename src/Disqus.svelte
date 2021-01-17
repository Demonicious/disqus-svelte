<script>
    import DisqusThread from "./action.js";

    export let container  = "disqus_container";
    export let url        = window.location.href;
    export let identifier = window.location.pathname;
    export let siteName = "svelte-test"
</script>

<div use:DisqusThread={{
    identifier,
    url,
    siteName
}} class={container} />