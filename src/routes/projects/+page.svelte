<script lang="ts">
    import ProjectListItem from "$lib/components/projects/ProjectListItem.svelte";
    import projects from "$lib/projects/projects.json"
</script>

<section class="flex flex-col w-full items-center justify-start px-8 sm:px-16 py-10 text-xl text-primary-foreground flex-grow">
    <h2 class="text-3xl font-semibold text-left w-full text-secondary-foreground">Projects</h2>
    <div class="grid justify-center gap-x-12 gap-y-0 md:grid-cols-2 xl:grid-cols-3 2xl:grid-cols-4 3xl:grid-cols-5 self-center w-full sm:w-auto sm:flex sm:flex-wrap">
        {#each projects as project}
            <ProjectListItem projectName={project.projectName} description={project.projectDescr} imageSrc={project.imgSrc} wip={project.wip} path={project.path}/>
        {/each}
    </div>
</section>