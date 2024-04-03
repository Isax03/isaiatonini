<script lang="ts">
    import Navbar from "$lib/components/Navbar.svelte";
	import '../app.pcss';
</script>

<main class="min-h-[100svh]">
    <Navbar />
    <slot />
</main>