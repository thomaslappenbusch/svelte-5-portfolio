<script lang="ts">
	import Button1 from "$lib/components/Button1.svelte";
	import { ChevronLeft, ChevronRight, ExternalLinkIcon } from "lucide-svelte";
	import { fly } from "svelte/transition";

    let currentIndex = $state(0);
    let { data } = $props();

    function goNext() {
        currentIndex = (currentIndex + 1) % data.length;
    }

    function goPrev() {
        currentIndex = (currentIndex - 1 + data.length) % data.length;
    }

</script>

<div id="gallerySection" class="flex flex-col justify-start w-full mt-12">
    <div class="text-faint text-xs font-extrabold uppercase">Gallery</div>
    <div class="w-full h-[450px] mt-6 rounded-md bg-radial from-background-secondary to-background overflow-hidden relative border border-background-tertiary">
        <div class="absolute inset-0 flex items-center justify-center">
            {#key currentIndex}
                <div 
                    in:fly={{ y: 4, duration: 150, delay: 150 }} 
                    out:fly={{ y: 4, duration: 150 }}
                    class="absolute inset-0 flex items-center justify-center"
                >
                    <div class="relative m-14 mt-8">
                        <!-- svelte-ignore a11y_missing_attribute -->
                         {#if data[currentIndex].image != null }
                            <img 
                                src={data[currentIndex].image} 
                                class="object-contain max-h-[350px] rounded-md"
                            />
                        {:else}
                            {@const Component = data[currentIndex].component}
                            <Component />
                        {/if}
                        
                        <div class="absolute -bottom-8 left-1/2 -translate-x-1/2 text-faint text-xs text-center font-medium min-w-[300px]">
                            {data[currentIndex].text}
                        </div>
                    </div>
                </div>
            {/key}
        </div>
        <div class="flex space-x-2 absolute bottom-2 left-3 text-faint/70 text-xs">
            {currentIndex+1}
            /
            {data.length}
        </div>
        <div class="flex space-x-2 absolute bottom-2 right-2">
            <button onclick={goPrev} aria-label="goLeftGallery" class="w-8 h-8 cursor-pointer bg-background hover:bg-background-secondary/50 text-[#EEEEE4] rounded-full flex items-center justify-center border border-background-tertiary">
                <ChevronLeft class="h-4 w-4"/>
            </button>
            <button onclick={goNext} aria-label="goLeftGallery" class="w-8 h-8 cursor-pointer bg-background hover:bg-background-secondary/50 text-[#EEEEE4] rounded-full flex items-center justify-center border border-background-tertiary">
                <ChevronRight class="h-4 w-4"/>
            </button>
        </div>
    </div>
</div>