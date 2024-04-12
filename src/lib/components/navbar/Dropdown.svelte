<script lang="ts">
    import { ChevronDown } from "lucide-svelte";
    import projects from "$lib/projects/projects.json";
    import { page } from "$app/stores";
    import WipBadge from "../projects/WipBadge.svelte";
    import { goto } from "$app/navigation";

    let isDropdownOpen = false; // default state (dropdown close)

    const handleDropdownClick = () => {
        isDropdownOpen = !isDropdownOpen; // togle state on click
    };

    const handleDropdownFocusLoss = ({
        relatedTarget,
        currentTarget,
    }: {
        relatedTarget: EventTarget | null;
        currentTarget: HTMLElement;
    }) => {
        // sleep 200ms to check if the focus is still within the dropdown
        setTimeout(() => {
            if (
                relatedTarget instanceof HTMLElement &&
                currentTarget.contains(relatedTarget)
            )
                return;
            isDropdownOpen = false;
        }, 200);
    };
</script>

<div class="sm:flex justify-between items-center hidden">
    <button on:click={handleDropdownClick} on:focusout={handleDropdownFocusLoss} >
        <ChevronDown class="w-6 h-6" />
    </button>
    <div class="relative">
        <ul
            class="absolute m-auto left-[-2.75rem] top-5 w-max bg-zinc-700 rounded-xl p-4 flex flex-col gap-4
                {isDropdownOpen
                    ? 'box'
                    : 'hidden'
                }
            "
        >
            {#each projects as project}
                <li>
                    <button
                        on:click={() => {
                            if (!project.wip) {
                                isDropdownOpen = false;
                                goto(project.path);
                            }
                        }}
                        class="w-full justify-between flex gap-3
                            {$page.url.pathname.includes(project.path)
                                ? 'text-secondary-foreground font-medium'
                                : 'text-primary-foreground'}
                            {project.wip
                                ? 'cursor-default'
                                : 'cursor-pointer'
                            }
                        "
                    >
                        {project.projectName}
                        {#if project.wip}
                            <WipBadge />
                        {/if}
                    </button>
                </li>
            {/each}
        </ul>
    </div>
</div>
