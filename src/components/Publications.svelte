<script>
    export let publications;
    let show = false;
</script>

  
<div class="p-4 sm:p-6 md:p-8 flex flex-col gap-4 rounded-lg border border-solid border-violet-700 text-center group cursor-pointer hover:border-violet-400 duration-200">
  <div class="bg-slate-950 grid place-items-center px-4 text-5xl md:text-6xl -mt-10 sm:-mt-12 md:-mt-14 lg:-mt-16 mx-auto duration-200">
    <h3 class="font-medium text-xl sm:text-2xl md:text-3xl"><span class="poppins text-violet-400">{publications.journal}</span></h3>
  </div>
    
  <div>
    <h3 class="font-semibold text-2xl sm:text-3xl md:text-2xl">{publications.title}</h3>
  </div>

  <!-- Only shows first sentence of abstract and reveals the rest upon clicking -->
  <div>
    <button on:click={() => show = !show}><span class="poppins text-violet-300">{publications.abstractabbr}</span></button>
    {#if show}
    <p>{publications.abstract}</p>
    {/if}
  </div>
    <slot/>
  <a href={publications.href} target="_blank">
    <div class="flex-1 flex justify-between gap-4 items-center">
      <div class="ml-auto cursor-pointer hover:text-slate-950 duration-200 relative after:absolute after:top-0 after:h-0 after:right-full after:w-full after:h-full after:bg-white after:duration-200 hover:after:translate-x-full after:z-[-1] overflow-hidden">
        <p>{publications.citation}</p>
        <p class="relative z-4">Go to &rarr;</p>
      </div>
    </div>
  </a>  
</div>