<script lang="ts">
    import ProjectFeature from "$lib/components/projects/ProjectFeature.svelte";
    import Github from 'svelte-material-icons/Github.svelte';

    let controllerDesc = "Android application that allows you to control PTZ cameras through the VISCA protocol. The app supports multiple cameras and provides an intuitive interface to move the camera, adjust zoom and focus, and save custom presets. It also offers a live video feed from the camera.";
</script>

<div class="px-5 mt-12 mb-20 w-full items-center flex flex-col gap-12 text-primary-foreground">
    <div class="flex items-center gap-4">
        <p class="text-xl">
            <span class="text-secondary-foreground font-medium text-2xl">Goal:</span>
            A solution to remotely control <b>PTZ cameras</b>, in a <b>flexible</b> way
        </p>
        <a href="https://github.com/PTZ-Vision/PTZ-Vision-Android" target="_blank" rel="noopener noreferrer" class="text-zinc-400 hover:text-secondary-foreground transition-colors">
            <Github size="1.5em"/>
        </a>
    </div>
    <div class="flex flex-col gap-10">
        <ProjectFeature
            title="Cameras Controller"
            description={controllerDesc}
            imageSrc={null}
        />
        <p class="text-base text-center">
            Frontend with <a
                href="https://developer.android.com/compose"
                class="text-secondary-foreground">Jetpack Compose</a
            ><br />
            Local Data Persistence with <a
				href="https://developer.android.com/jetpack/androidx/releases/room"
				class="text-secondary-foreground">Room DB</a>
            <br />
        </p>
    </div>
</div>
