<script>
	import { text } from "@sveltejs/kit";


	import { CodeSquareIcon } from "lucide-svelte";

    let { data } = $props();

</script>
<div id="experienceSection" class="flex flex-col justify-start w-full">
    <div class="text-faint text-xs font-extrabold uppercase">Technical Skills</div>
    <div class="flex flex-wrap mt-4 gap-1.5">
        {#each data as skill}
            <div class="flex items-center justify-center py-1 px-1.5 text-tertiary text- font-medium text-xs space-x-[5px] bg-background-tertiary rounded-md border border-background-secondary">
                {@html skill.icon}
                <div>{skill.text}</div>
            </div>
        {/each}
    </div>
</div>