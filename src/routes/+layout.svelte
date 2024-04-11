<script lang="ts">
    import Footer from "$lib/components/footer/Footer.svelte";
    import Navbar from "$lib/components/navbar/Navbar.svelte";
	import '../app.pcss';
</script>

<main class="min-h-[100svh] flex flex-col">
    <Navbar />
    <slot/>
</main>
<Footer />