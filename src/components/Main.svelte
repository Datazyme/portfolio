<script>
  import Step from "../components/Step.svelte"
  let steps = [
    {name: 'unitConverter', icon: 'fa-solid fa-calculator', href:'https://unit-converter-ashy.vercel.app'},
    {name: 'Twisted Stitch', icon: "fa-solid fa-car", href:'https://twisted-stitch.vercel.app'},
    {name: 'West Coast Mushrooms', icon: 'fa-solid fa-diagram-project', href:'https://west-coast-mushrooms-psi-inky-50.vercel.app'},
  ] 
  let benefits = [
    {
      metric: "10x",
      name: "a self taught developer",
      description:
        "I taught myself to code using free online resources and absolutely fell in love with the creativity and problem solving that is involved in developing and engineering innovative new online experiences. Starting of with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much much more.",
    },
    {
      name: "a product design & UX fanatic",
      description:
        "Carefully crafting and designing amazing user experiences allows me to express and experiment with every morsel of creativity I have. I love the challenge of learning new design concepts and enabling users with amazing online experiences.",
    },
    {
      name: "an excellent communicator",
      description:
        "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
    },
  ];
</script>
<!--- _blank opens up link in a new page  -->
<main class="flex flex-col flex-1 p-4">
  <section id="introPage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14">

    <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
       Welcome to <span class="poppins text-violet-400">PortiaBella Designs</span> by Anastasia 
      </h2>
      <h2 class="font-semibold text-4xl sm:text-4xl md:text-4xl"><span class="poppins text-violet-400">Full Stack Web Development</span> and More
      </h2>
      
      <p class="text-base sm:text-lg md:text-xl">
        Scroll down to see my <span class="text-violet-400">website designs, science research experience, photography and clothing designs.</span>
      </p>
      <a class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950" href="https://www.cbc.ca/news" target="_blank">
        
        <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
       />
      <h4 class="relative z-9">Get in touch &rarr;</h4>
      </a>
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img src={"images/logo1.png"} alt="logo1"
      class="object-cover z-[2] max-h-[70hv]"/>
    </div>
  </section>

  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h2 class="font-semibold text-3xl sm:text-4xl md:text-6xl">
        <span class="poppins text-violet-400">Websites</span> 
      </h2>

    </div>
      <a href="https://github.com/Datazyme" target="_blank" 
      class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200">
      <!-- <i class="fa-regular fa-circle-play"></i> -->
      <p>GitHub</p>
    </a>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      <Step step={steps[0]}>
        <img src={"images/unitConverter.png"} alt="unitConverter"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>unitConverter is an app which converts a variety of units of measure. It was created with <strong class="text-violet-400">Javascript, NodeJS + Express, SASS and jQuery.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p>
      </Step>
      <Step step={steps[1]}>
        <img src={"images/twistedStitch.png"} alt="twistedStitch"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>unitConverter is an app which converts a variety of units of measure. It was created with <strong class="text-violet-400">Javascript, NodeJS + Express, SASS and jQuery.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p></Step>
      <Step step={steps[2]}>
        <img src={"images/westCoastMushrooms.png"} alt="westCoastMushrooms"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>unitConverter is an app which converts a variety of units of measure. It was created with <strong class="text-violet-400">Javascript, NodeJS + Express, SASS and jQuery.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p>
      </Step>
    </div>

  </section>

  <section id="about" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
    <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
    <h6 class="text-5xl sm:text-xl md:text-2xl">Want to know more?</h6>
    <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">A bit <span class="poppins text-violet-400">about</span> me</h3>
  </div>
  <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">I am . . .</p>
  <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
    {#each benefits as benefit, index}
    <div class="flex gap-6 sm:gap-8" >
      <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">
        0{index+1}
      </p>
      <div class="flex flex-col gap-6 sm:gap-8">
        <h3 class="text-2xl sm:text-3xl md:text-5xl">
          {benefit.name}
        </h3>
        <p>{benefit.description}</p>        
      </div>
    </div>
    {/each}
  </div>
  <h5 class={" text-2xl sm:text-3xl font-semibold text-center poppins "}>The <span class="text-violet-400 poppins">Complete</span> Package</h5>
  
  <div class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full">
    <table class="bg-white text-slate-700 rounded text-center">
      <thead class="border-b border-solid border-slate-200 ">
        <tr class="">
          <th />
          <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
          <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
          <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
          <th class="whitespace-nowrap bg-violet-700 text-white p-4 px-8">Me</th>
        </tr>
      </thead>
      <tbody>
        <tr class="border-b border-solid border-slate-200">
          <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Dedication</td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
        </tr>
        <tr class="border-b border-solid border-slate-200">
          <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Critical Thought</td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
        <tr class="border-b border-solid border-slate-200">
          <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Iterpersonal Skills</td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
        </tr>
        <tr class="border-b border-solid border-slate-200">
          <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm whitespace-nowrap">Programming Ability</td>
          <td><i class="fa-solid fa-xmark text-slate-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
          <td><i class="fa-solid fa-check text-green-500"></i></td>
      </tbody>
    </table>
  </div>
  <div class="mx-auto -mt-12 italic sm:hidden opacity-50">
    <p>Scroll to see more &rarr;</p>
  </div>
  <p class="mx-auto">So why not invest?</p>
  </section>
</main>