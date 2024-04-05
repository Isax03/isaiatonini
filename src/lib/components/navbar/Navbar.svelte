<script lang="ts">
    import { Menu, X } from 'lucide-svelte';
	import Github from 'svelte-material-icons/Github.svelte';
	import Linkedin from 'svelte-material-icons/Linkedin.svelte';
	import Instagram from 'svelte-material-icons/Instagram.svelte';
    import Drawer from './Drawer.svelte';
    import { sineIn } from 'svelte/easing';
    import Logo from './Logo.svelte';
    import NavList from './NavList.svelte';

	let transitionParamsRight = {
		x: 200,
		duration: 200,
		easing: sineIn
	};
	let hidden = true;

	let closed = true;
	const triggerMenu = () => {
		const sidebar = document.getElementById('sidebar');
		sidebar!.classList.toggle('hidden');
		sidebar!.classList.toggle('flex');
	}
</script>

<nav class="flex bg-zinc-800 sticky w-full">
	<div class="flex py-2 px-3 gap-4 justify-between w-full">
		<Logo />
		<div class="w-full">
			<div class="w-full h-full flex flex-row items-center justify-end px-6 sm:justify-between relative sm">
				<button on:click={()=>hidden = false} class="z-[9999] cursor-pointer sm:hidden" >
					<Menu class="text-white w-8 h-8"/>
				</button>
				<div class="sm:flex h-full items-center justify-between hidden w-full">
					<NavList/>
					<div class="flex gap-4">
						<a href="https://github.com/Isax03" target="_blank">
							<Github class="dark:text-white text-white w-8 h-8" />
						</a>
						<a href="https://linkedin.com/in/isaiatonini" target="_blank">
							<Linkedin class="dark:text-white text-white w-8 h-8" />
						</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</nav>

<Drawer backdrop={false} class="z-[100]" placement="right" transitionType="fly" transitionParams={transitionParamsRight} bind:hidden>	
	<div>
		<div class="flex items-center justify-between py-4">
			<h4 class="flex items-center text-2xl sm:text-3xl font-light text-white">
				Menu
			</h4>
			<button on:click={() => {hidden = true}} class="text-white">
				<X class="w-8 h-8"/>
			</button>
		</div>
		<hr class="dark:border-gray-600"/>
		<section class="z-50 mt-8 flex-col items-center justify-between px-4">
			<NavList bind:hidden/>
		</section>
	</div>
	<div class="flex gap-4 items-center justify-center mb-10">
		<a href="https://github.com/Isax03" target="_blank">
			<Github class="dark:text-white text-white w-8 h-8" />
		</a>
		<a href="https://linkedin.com/in/isaiatonini" target="_blank">
			<Linkedin class="dark:text-white text-white w-8 h-8" />
		</a>
		<a href="https://www.instagram.com/isa.toni03/" target="_blank">
			<Instagram class="dark:text-white text-white w-8 h-8" />
		</a>
	</div>
</Drawer>