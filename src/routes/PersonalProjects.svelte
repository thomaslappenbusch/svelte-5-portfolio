<script>
	import { ExternalLinkIcon } from "lucide-svelte";
    let { data } = $props();
</script>

<div id="experienceSection" class="flex flex-col justify-start w-full mt-12">
    <div class="text-faint text-xs font-extrabold uppercase">Personal projects</div>
    <div class="grid items-start justify-center mt-6 grid-cols-1 gap-6 sm:grid-cols-2">
        {#each data as project}
            <div class="p-4 flex flex-col bg-radial from-background-secondary to-background rounded-md border border-background-tertiary">
                <img 
                    src={project.image} 
                    class="w-full aspect-video bg-background-tertiary rounded-md origin-top object-fill"
                />   
                <div class="flex flex-col h-full mt-4">
                    <div class="flex justify-between items-center">
                        <div class="text-xl font-medium text-primary flex items-center">{project.name}
                            <a 
                                href={project.link} 
                                target="_blank" 
                                rel="noopener noreferrer"
                                class="p-1 m-1 hover:bg-faint/20 transition cursor-pointer rounded-md text-secondary text-xs flex items-center"
                            >
                                <ExternalLinkIcon class="h-3.5 w-3.5" strokeWidth={1.5}/>
                            </a>
                        </div>
                        <div class="text-xs text-faint font-medium">
                            {project.technology}
                        </div>
                    </div>
                    <div class="text-secondary mt-4 mb-2 text-sm">
                        {project.description}
                    </div>
                </div>
            </div>
        {/each}
    </div>
</div>