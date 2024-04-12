<script lang="ts">
	export let imageSrc: string = "https://via.placeholder.com/150";
	export let title: string;
	export let description: string;
	export let inverted: boolean = false;
</script>

<div class="flex flex-col sm:flex-row gap-10 items-center text-primary-foreground max-w-[48rem]">
	{#if !inverted}
		<img src={imageSrc} alt="Project" class="rounded-lg hidden sm:block max-h-[30rem] w-max h-max max-w-96" />
	{/if}
	<div class="flex flex-col gap-6 {inverted ? 'sm:items-end' : 'items-start'}">
		<h1 class="text-2xl font-semibold text-secondary-foreground">{title}</h1>
		<img src={imageSrc} alt="Project" class="self-center rounded-lg sm:hidden max-h-96 w-max" />
		<div>
			{#each description.split('\n') as desc}
				<p class="{inverted ? 'sm:text-end' : 'text-start'}">{desc}</p>
			{/each}
		</div>
	</div>
	{#if inverted}
		<img src={imageSrc} alt="Project" class="rounded-lg hidden sm:block max-h-[30rem] w-max h-max max-w-96" />
	{/if}
</div>