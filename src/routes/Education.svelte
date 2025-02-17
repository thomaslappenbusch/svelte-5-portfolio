<script lang="ts">

    let { data } = $props();
    
</script>

<div id="educationSection" class="flex flex-col justify-start w-full">
    <div class="text-faint text-xs font-extrabold uppercase">Education</div>
    <div class="flex flex-col items-start justify-center mt-4">
        <div class="flex w-full">
            <div class="flex flex-col items-center shrink-0">
                <img 
                    src={data.image} 
                    alt="{data.school} logo"
                    class="h-12 w-12 rounded-full shrink-0"
                />
            </div>
            <div class="flex ml-3 flex-col grow pb-14">
                <div class="flex justify-between items-center w-full h-12">
                    <div class="flex flex-col justify-start items-start">
                        <div class="text-primary text-xl font-semibold">
                            {data.school}
                        </div>
                        <div class="text-faint text-xs -mt-[1px]">
                            {data.degree}
                        </div>
                    </div>
                    <div class="text-tertiary text-sm flex items-center">
                        {data.graduationYear}
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>