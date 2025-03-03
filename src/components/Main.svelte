<script>
  import Step from "../components/Step.svelte"
  import Publications from "./Publications.svelte";
  let steps = [
    {name: 'unitConverter', icon: 'fa-solid fa-calculator', href:'https://unit-converter-ashy.vercel.app'},
    {name: 'Twisted Stitch', icon: "fa-solid fa-shirt", href:'https://twisted-stitch.vercel.app'},
    {name: 'West Coast Mushrooms', icon: "fa-solid fa-frog", href:'https://west-coast-mushrooms-psi-inky-50.vercel.app'},
    {name: 'To Do List', icon: "fa-solid fa-frog", href:'https://todo-remult-nextjs-anastasias-projects-8c761283.vercel.app/api/auth/signin?callbackUrl=https%3A%2F%2Ftodo-remult-nextjs-anastasias-projects-8c761283.vercel.app%2F'},
  ] 
  let education = [
    {
      metric: "10x",
      name: "Lighthouse Labs",
      description:
        "Diploma in Web Development",
    },
    {
      name: "Simon Fraser University",
      description:
        "Master of Science.",
    },
    {
      name: "University of Toronto",
      description:
        "Bachelor of Science",
    },
  ];

  let publications = [
    {
      title:"Transcription shapes genome-wide histone acetylation patterns.",
      authors: "Benjamin J.E. Martin, Julie Brind’Amour, Kristoffer N. Jensen†, Anastasia Kuzmin, Zhen Cheng Liu, Matthew Lorincz and LeAnn J. Howe.",
      journal: "Nature Communications",
      citation: "Nat Commun. 2021 Jan 11;12(1):210. doi: 10.1038/s41467-020-20543-z. PMID: 33431884; PMCID: PMC7801501.",
      href: "https://pmc.ncbi.nlm.nih.gov/articles/PMC7801501/",
      abstract: "Histone acetylation is a ubiquitous hallmark of transcription, but whether the link between histone acetylation and transcription is causal or consequential has not been addressed. Using immunoblot and chromatin immunoprecipitation-sequencing in S. cerevisiae, here we show that the majority of histone acetylation is dependent on transcription. This dependency is partially explained by the requirement of RNA polymerase II (RNAPII) for the interaction of H4 histone acetyltransferases (HATs) with gene bodies. Our data also confirms the targeting of HATs by transcription activators, but interestingly, promoter-bound HATs are unable to acetylate histones in the absence of transcription. Indeed, HAT occupancy alone poorly predicts histone acetylation genome-wide, suggesting that HAT activity is regulated post-recruitment. Consistent with this, we show that histone acetylation increases at nucleosomes predicted to stall RNAPII, supporting the hypothesis that this modification is dependent on nucleosome disruption during transcription. Collectively, these data show that histone acetylation is a consequence of RNAPII promoting both the recruitment and activity of histone acetyltransferases."
    },
    {
      title: "The limit to evolutionary rescue depends on ploidy in yeast exposed to nystatin.",
      authors: "Jasmine Ono, Anastasia Kuzmin, Lesley Miller, Sarah P Otto",
      journal: "Canadian Journal of Microbiology.",
      citation: "Can J Microbiol. 2024 Sep 1;70(9):394-404. doi: 10.1139/cjm-2023-0235. Epub 2024 Jun 14. PMID: 38875715.",
      href: "https://cdnsciencepub.com/doi/full/10.1139/cjm-2023-0235?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org",
      abstract: "The number of copies of each chromosome, or ploidy, of an organism is a major genomic factor affecting adaptation. We set out to determine how ploidy can impact the outcome of evolution, as well as the likelihood of evolutionary rescue, using short-term experiments with yeast (Saccharomyces cerevisiae) in a high concentration of the fungicide nystatin. In similar experiments using haploid yeast, the genetic changes underlying evolutionary rescue were highly repeatable, with all rescued lines containing a single mutation in the ergosterol biosynthetic pathway. All of these beneficial mutations were recessive, which led to the expectation that diploids would find alternative genetic routes to adaptation. To test this, we repeated the experiment using both haploid and diploid strains and found that diploid populations did not evolve resistance. Although diploids are able to adapt at the same rate as haploids to a lower, not fully inhibitory, concentration of nystatin, the present study suggests that diploids are limited in their ability to adapt to an inhibitory concentration of nystatin, while haploids may undergo evolutionary rescue. These results demonstrate that ploidy can tip the balance between adaptation and extinction when organisms face an extreme environmental change.",
    }
  ]
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
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img src={"images/logo1.png"} alt="logo1"
      class="object-cover z-[2] max-h-[70hv]"/>
    </div>
  </section>

  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
      <h2 class="font-semibold text-3xl sm:text-4xl md:text-6xl text-center">My <span class="poppins text-violet-400">Websites</span></h2>
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
        <p>unitConverter is an app which converts a variety of units of measure. It was built with <strong class="text-violet-400">Javascript, NodeJS + Express, SASS and jQuery.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p>
      </Step>
      <Step step={steps[1]}>
        <img src={"images/twistedStitch.png"} alt="twistedStitch"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>Twisted Stitch is an online store selling hand knit clothing. It was built with <strong class="text-violet-400">Next.js, Tailwind and Stripe.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p></Step>
      <Step step={steps[2]}>
        <img src={"images/westCoastMushrooms.png"} alt="westCoastMushrooms"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>West Coast Mushrooms is dedicated to providing images and information about mushrooms found on the Candian west coast.  It was built with <strong class="text-violet-400">React and CSS.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p>
      </Step>
      <Step step={steps[3]}>
        <img src={"images/toDORemult.png"} alt="To Do List"
        class="object-cover z-[2] max-h-[70hv]"/>
        <p>A to-do app where you can add, check off and delete tasks. It was built with <strong class="text-violet-400">Next.js, remult, supabase postgres and Tailwind CSS.</strong> It is hosted on <strong class="text-violet-400">Vercel</strong></p>
      </Step>
    </div>

  </section>

  <section id="education" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
    <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
      <h2 class="font-semibold text-3xl sm:text-4xl md:text-6xl text-center">My <span class="poppins text-violet-400">Education</span></h2>
    </div>
 
  <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
    {#each education as program, index}
    <div class="flex gap-6 sm:gap-8" >
      <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">
        0{index+1}
      </p>
      <div class="flex flex-col gap-6 sm:gap-8">
        <h3 class="text-2xl sm:text-3xl md:text-5xl">
          {program.name}
        </h3>
        <h4 class="text-violet-400 text-2xl sm:text-3xl md:text-3xl">{program.description}</h4>        
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
  <section id="publications" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
      <h2 class="font-semibold text-3xl sm:text-4xl md:text-6xl text-center">My <span class="poppins text-violet-400">Publications</span></h2>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      <Publications publications={publications[0]}>
        <img src={"images/unitConverter.png"} alt="unitConverter"
        class="object-cover z-[2] max-h-[70hv]"/>
      </Publications>
      <Publications publications={publications[1]}>
        <img src={"images/twistedStitch.png"} alt="twistedStitch"
        class="object-cover z-[2] max-h-[70hv]"/>
      </Publications>
    </div>

  </section>
</main>