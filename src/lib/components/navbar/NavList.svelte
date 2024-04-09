<script>
	import { page } from '$app/stores';

	let routes = [
		{
			name: 'Home',
			path: '/'
		},
		{
			name: 'Projects',
			path: '/projects'
		},
		{
			name: 'Contact',
			path: '/contact'
		}
	];

	export let hidden=true;
</script>

<ul class="flex flex-col mt-10 sm:ml-10 sm:mt-0 sm:flex-row sm:w-max sm:h-full sm:items-center justify-start items-start gap-7 sm:gap-8">
	{#each routes as route}
		<li class={`flex items-center gap-2 sm:text-xl ${route.path == $page.url.pathname ? 'text-secondary-foreground' : 'text-primary-foreground'}`}>
			<a href={route.path} on:click={()=> hidden = true}>{route.name}</a>
		</li>
	{/each}
</ul>