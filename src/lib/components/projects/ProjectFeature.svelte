<script lang="ts">
    export let imageSrc: string | null = null;
    export let title: string;
    export let description: string;
    export let inverted: boolean = false;
</script>

<div class="flex flex-col sm:flex-row gap-10 items-center text-primary-foreground max-w-[48rem]">
    {#if !inverted}
        {#if imageSrc}
            <img src={imageSrc} alt="Project" class="rounded-lg hidden sm:block max-h-[30rem] w-max h-max max-w-96 shadowCard" />
        {:else}
            <div class="hidden sm:flex items-center justify-center rounded-lg bg-zinc-800 w-96 h-64">
                <p class="text-zinc-400">No preview available</p>
            </div>
        {/if}
    {/if}
    <div class="flex flex-col gap-6 {inverted ? 'sm:items-end' : 'items-start'} w-full">
        <h1 class="text-2xl font-semibold text-secondary-foreground">{title}</h1>
        {#if imageSrc}
            <img src={imageSrc} alt="Project" class="self-center rounded-lg sm:hidden max-h-96 w-max shadowCard" />
        {:else}
            <div class="flex sm:hidden items-center justify-center rounded-lg bg-zinc-800 w-full h-48">
                <p class="text-zinc-400">No preview available</p>
            </div>
        {/if}
        <div>
            {#each description.split('\n') as desc}
                <p class="{inverted ? 'sm:text-end' : 'text-start'}">{desc}</p>
            {/each}
        </div>
    </div>
    {#if inverted}
        {#if imageSrc}
            <img src={imageSrc} alt="Project" class="rounded-lg hidden sm:block max-h-[30rem] w-max h-max max-w-96 shadowCard" />
        {:else}
            <div class="hidden sm:flex items-center justify-center rounded-lg bg-zinc-800 w-96 h-64">
                <p class="text-zinc-400">No preview available</p>
            </div>
        {/if}
    {/if}
</div>

<style>
    .shadowCard {
        box-shadow: 0px 0px 10px #2bfc93
    }
</style>