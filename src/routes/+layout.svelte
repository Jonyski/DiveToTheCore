<script>
    import "../global.css";
    let { children } = $props();
    import Navbar from "$lib/Navbar.svelte";
</script>

<Navbar />

{@render children()}
