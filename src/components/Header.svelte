<script>
  export let y;
  let tabs = [
    {name:'Projects', link:'#projects'},
    {name:'Education', link:'#education'},
    {name:'Publications', link:'#publications'},
  ]
</script>

<header class={"sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-b border-solid " + (
  y > 0 ? 'py-4 bg-slate-950 border-violet-950' : "py-6 bg-transparent border-transparent"
)}>
  <h1 class="font-medium">
    <b class="font-bold poppins sm:text-lg md:text-4xl poppins text-violet-200">AK</b>
  </h1>
  <div class="sm:flex items-center gap-4 hidden sm:text-lg md:text-2xl">
    {#each tabs as tab, index} 
    <a href={tab.link} class="duration-200 hover:text-violet-400">
      <p>{tab.name}</p></a>{/each}
  </div>
  <a href="https://www.linkedin.com/in/anastasia-kuzmin-b6456a287" target="_blank" class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950">
    <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-80 group-hover:translate-x-full z-0 duration-200"></div>
    <h4 class="relative z-9">LinkedIn</h4>
  </a>
  <a href="https://www.instagram.com/leafskywaterfungi/" target="_blank">
    <img class="h-12 w-12 object-scale-down" src={"images/instagram.png"} alt="instagram"
    />
  </a>
</header>

