<script lang="ts">
    import { Menu, X } from 'lucide-svelte';
    import Drawer from './Drawer.svelte';
    import { sineIn } from 'svelte/easing';
    import Logo from './Logo.svelte';
    import NavList from './NavList.svelte';
    import Socials from './Socials.svelte';

	let transitionParamsRight = {
		x: 200,
		duration: 200,
		easing: sineIn
	};
	let hidden = true;
</script>

<nav class="flex bg-zinc-800 sticky top-0 w-full">
	<div class="flex py-2 px-3 gap-4 justify-between items-center w-full">
		<Logo />
		<div class="w-full">
			<div class="w-full h-full flex flex-row items-center justify-end px-6 sm:justify-between relative">
				<button on:click={()=>hidden = false} class="z-[9999] cursor-pointer sm:hidden" >
					<Menu class="text-primary-foreground w-8 h-8"/>
				</button>
				
				<div class="sm:flex h-full items-center justify-between hidden w-full">
					<NavList/>
					<Socials/>
				</div>
			</div>
		</div>
	</div>
</nav>

<Drawer backdrop={false} class="z-[100] sm:hidden" placement="right" transitionType="fly" transitionParams={transitionParamsRight} bind:hidden>	
	<div>
		<div class="flex items-center justify-between py-4">
			<h4 class="flex items-center text-2xl sm:text-3xl font-light text-primary-foreground">
				Menu
			</h4>
			<button on:click={() => {hidden = true}} class="text-primary-foreground">
				<X class="w-8 h-8"/>
			</button>
		</div>
		<hr/>
		<section class="z-50 mt-2 flex-col items-center justify-between px-4">
			<NavList bind:hidden/>
		</section>
	</div>
	<Socials/>
</Drawer>