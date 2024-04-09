<script lang="ts">
    import WipBadge from "./WipBadge.svelte";

	export let imageSrc: string = "https://via.placeholder.com/160x90";
	export let projectName: string;
	export let description: string;
	export let wip: boolean = false;
</script>

<div class="flex flex-col gap-4 mt-10 w-full sm:w-72 p-5 rounded-2xl shadowCard border-[3px] border-zinc-600">
	<h3 class="text-base font-semibold text-primary-foreground flex gap-4">
		{projectName}
		{#if wip}
			<WipBadge />
		{/if}
	</h3>

	<img src={imageSrc} alt="{projectName}" class="w-full aspect-video rounded-lg" />

	<div class="w-full hidden sm:block text-left text-wrap">
		<p class="text-primary-foreground text-sm line-clamp-3">{description}</p>
	</div>
</div>

<style>
	.shadowCard {
		box-shadow: 0px 0px 6px #2bfc93
	}
</style>