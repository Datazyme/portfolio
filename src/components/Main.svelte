<script>
  import Step from "../components/Step.svelte"
  import Publications from "./Publications.svelte";

  // List of website objects
  let steps = [
    {name: 'unitConverter', icon: 'fa-solid fa-calculator', href:'https://unit-converter-ashy.vercel.app'},
    {name: 'Twisted Stitch', icon: "fa-solid fa-shirt", href:'https://twisted-stitch.vercel.app'},
    {name: 'West Coast Mushrooms', icon: "fa-solid fa-frog", href:'https://west-coast-mushrooms-psi-inky-50.vercel.app'},
    {name: 'To Do List', icon: "fa-solid fa-frog", href:'https://todo-remult-nextjs-anastasias-projects-8c761283.vercel.app/api/auth/signin?callbackUrl=https%3A%2F%2Ftodo-remult-nextjs-anastasias-projects-8c761283.vercel.app%2F'},
  ];

  // List of education objects
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

  // List of publication objects
  let publications = [
    {
      title:"Transcription shapes genome-wide histone acetylation patterns.",
      journal: "Nature Communications",
      citation: "Nat Commun. 2021 Jan 11;12(1):210. doi: 10.1038/s41467-020-20543-z. PMID: 33431884; PMCID: PMC7801501.",
      href: "https://pmc.ncbi.nlm.nih.gov/articles/PMC7801501/",
      abstractabbr: "Histone acetylation is a ubiquitous hallmark of transcription, but whether the link between histone acetylation and transcription is causal or consequential has not been addressed.",
      abstract: "Using immunoblot and chromatin immunoprecipitation-sequencing in S. cerevisiae, here we show that the majority of histone acetylation is dependent on transcription. This dependency is partially explained by the requirement of RNA polymerase II (RNAPII) for the interaction of H4 histone acetyltransferases (HATs) with gene bodies. Our data also confirms the targeting of HATs by transcription activators, but interestingly, promoter-bound HATs are unable to acetylate histones in the absence of transcription. Indeed, HAT occupancy alone poorly predicts histone acetylation genome-wide, suggesting that HAT activity is regulated post-recruitment. Consistent with this, we show that histone acetylation increases at nucleosomes predicted to stall RNAPII, supporting the hypothesis that this modification is dependent on nucleosome disruption during transcription. Collectively, these data show that histone acetylation is a consequence of RNAPII promoting both the recruitment and activity of histone acetyltransferases."
    },
    {
      title: "The limit to evolutionary rescue depends on ploidy in yeast exposed to nystatin.",
      journal: "Canadian Journal of Microbiology",
      citation: "Can J Microbiol. 2024 Sep 1;70(9):394-404. doi: 10.1139/cjm-2023-0235. Epub 2024 Jun 14. PMID: 38875715.",
      abstractabbr: "The number of copies of each chromosome, or ploidy, of an organism is a major genomic factor affecting adaptation.",
      href: "https://cdnsciencepub.com/doi/full/10.1139/cjm-2023-0235?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org",
      abstract: "We set out to determine how ploidy can impact the outcome of evolution, as well as the likelihood of evolutionary rescue, using short-term experiments with yeast (Saccharomyces cerevisiae) in a high concentration of the fungicide nystatin. In similar experiments using haploid yeast, the genetic changes underlying evolutionary rescue were highly repeatable, with all rescued lines containing a single mutation in the ergosterol biosynthetic pathway. All of these beneficial mutations were recessive, which led to the expectation that diploids would find alternative genetic routes to adaptation. To test this, we repeated the experiment using both haploid and diploid strains and found that diploid populations did not evolve resistance. Although diploids are able to adapt at the same rate as haploids to a lower, not fully inhibitory, concentration of nystatin, the present study suggests that diploids are limited in their ability to adapt to an inhibitory concentration of nystatin, while haploids may undergo evolutionary rescue. These results demonstrate that ploidy can tip the balance between adaptation and extinction when organisms face an extreme environmental change.",
    },
    {
      title: "Too Much of a Good Thing: The Unique and Repeated Paths Toward Copper Adaptation.",
      journal: "Genetics",
      citation: "2015 Feb;199(2):555-71. doi: 10.1534/genetics.114.171124. Epub 2014 Dec 17. PMID: 25519894; PMCID: PMC4317662.",
      abstractabbr: "Copper is a micronutrient essential for growth due to its role as a cofactor in enzymes involved in respiration, defense against oxidative damage, and iron uptake.",
      href: "https://academic.oup.com/genetics/article/199/2/555/5935832",
      abstract: "Yet too much of a good thing can be lethal, and yeast cells typically do not have tolerance to copper levels much beyond the concentration in their ancestral environment. Here, we report a short-term evolutionary study of Saccharomyces cerevisiae exposed to levels of copper sulfate that are inhibitory to the initial strain. We isolated and identified adaptive mutations soon after they arose, reducing the number of neutral mutations, to determine the first genetic steps that yeast take when adapting to copper. We analyzed 34 such strains through whole-genome sequencing and by assaying fitness within different environments; we also isolated a subset of mutations through tetrad analysis of four lines. We identified a multilayered evolutionary response. In total, 57 single base-pair mutations were identified across the 34 lines. In addition, gene amplification of the copper metallothionein protein, CUP1-1, was rampant, as was chromosomal aneuploidy. Four other genes received multiple, independent mutations in different lines (the vacuolar transporter genes VTC1 and VTC4; the plasma membrane H+-ATPase PMA1; and MAM3, a protein required for normal mitochondrial morphology). Analyses indicated that mutations in all four genes, as well as CUP1-1 copy number, contributed significantly to explaining variation in copper tolerance. Our study thus finds that evolution takes both common and less trodden pathways toward evolving tolerance to an essential, but highly toxic, micronutrient.",
    },
    {
      title: "Loss-of-heterozygosity facilitates passage through Haldane’s sieve for Saccharomyces cerevisiae undergoing adaptation",
      journal: "Nature Communications",
      citation: "Nat Commun. 2014 May 7;5:3819. doi: 10.1038/ncomms4819. PMID: 24804896.",
      abstractabbr: "Haldane's sieve posits that the majority of beneficial mutations that contribute to adaptation should be dominant, as these are the mutations most likely to establish and spread when rare.",
      href: "https://www.nature.com/articles/ncomms4819",
      abstract: "It has been argued, however, that if the dominance of mutations in their current and previous environments are correlated, Haldane’s sieve could be eliminated. We constructed heterozygous lines of Saccharomyces cerevisiae containing single adaptive mutations obtained during exposure to the fungicide nystatin. Here we show that no clear dominance relationship exists across environments: mutations exhibited a range of dominance levels in a rich medium, yet were exclusively recessive under nystatin stress. Surprisingly, heterozygous replicates exhibited variable-onset rapid growth when exposed to nystatin. Targeted Sanger sequencing demonstrated that loss-of-heterozygosity (LOH) accounted for these growth patterns. Our experiments demonstrate that recessive beneficial mutations can avoid Haldane’s sieve in clonal organisms through rapid LOH and thus contribute to rapid evolutionary adaptation.",
    },
    {
      title: "Identification of Potentially Damaging Amino Acid Substitutions Leading to Human Male Infertility",
      journal: "Biology of Reproduction",
      citation: "Biol Reprod. 2009 Aug;81(2):319-26. doi: 10.1095/biolreprod.109.076000. Epub 2009 Apr 15. PMID: 19369647; PMCID: PMC2849822.",
      abstractabbr: "There are a number of known genetic alterations found in men with nonobstructive azoospermia, or testicular failure, such as Y microdeletions and cytogenetic abnormalities.",
      href: "https://pmc.ncbi.nlm.nih.gov/articles/PMC2849822/",
      abstract: "However, the etiology of nonobstructive azoospermia is unknown in the majority of men. The aim of this study was to investigate the possibility that unexplained cases of nonobstructive azoospermia are caused by nonsynonymous single-nucleotide polymorphisms (SNPs) in the coding regions of autosomal genes associated with sperm production and fertility. Using a candidate gene approach based on genetics of male infertility in mice, we resequenced nine autosomal genes from 78 infertile men displaying testicular failure using custom-made next-generation resequencing chips. Analysis of the data revealed several novel heterozygous nonsynonymous SNPs in four of nine sequenced genes in 14 of 78 infertile men. Eight SNPs in SBF1, three SNPs in LIMK2, two SNPs in LIPE, and one SNP in TBPL1 were identified. All of the novel mutations were in a heterozygous configuration, suggesting that they may be de novo mutations with dominant negative properties.",
    },
    {
      title: "The PcG Gene Sfmbt2 is Paternally Expressed in Extraembryonic Tissues.",
      journal: "Gene Expression Patterns",
      citation: "Gene Expr Patterns. 2008 Jan;8(2):107-16. doi: 10.1016/j.modgep.2007.09.005. Epub 2007 Oct 9. PMID: 18024232; PMCID: PMC2220043.",
      abstractabbr: "Genomic imprinting has dramatic effects on placental development, as has been clearly observed in interspecific hybrid, somatic cell nuclear transfer, and uniparental embryos",
      href: "https://pmc.ncbi.nlm.nih.gov/articles/PMC2220043/",
      abstract: " In fact, the earliest defects in uniparental embryos are evident first in the extraembryonic trophoblast. We performed a microarray comparison of gynogenetic and androgenetic mouse blastocysts, which are predisposed to placental pathologies, to identify imprinted genes. In addition to identifying a large number of known imprinted genes, we discovered that the Polycomb group (PcG) gene Sfmbt2 is imprinted. Sfmbt2 is expressed preferentially from the paternal allele in early embryos, and in later stage extraembryonic tissues. A CpG island spanning the transcriptional start site is differentially methylated on the maternal allele in e14.5 placenta. Sfmbt2 is located on proximal chromosome 2, in a region known to be imprinted, but for which no genes had been identified until now. This possibly identifies a new imprinted domain within the murine genome. We further demonstrate that murine SFMBT2 protein interacts with the transcription factor YY1, similar to the Drosophila PHO-RC.",
    },
  ];
  
  // Match game

  let initialCards = [
    { id: 1, value: "🍎", matched: false },
    { id: 2, value: "🍌", matched: false },
    { id: 3, value: "🍇", matched: false },
    { id: 4, value: "🍉", matched: false },
    { id: 5, value: "🍎", matched: false },
    { id: 6, value: "🍌", matched: false },
    { id: 7, value: "🍇", matched: false },
    { id: 8, value: "🍉", matched: false }
  ];

  let cards = [];
  let selected = [];
  let moves = 0;

  function shuffle(array) {
    return array.sort(() => Math.random() - 0.5);
  }

  function resetGame() {
    cards = shuffle([...initialCards.map(card => ({ ...card }))]); // Reset and shuffle
    selected = [];
    moves = 0;
  }

  function selectCard(card) {
    if (selected.length < 2 && !selected.includes(card) && !card.matched) {
      selected = [...selected, card];
    }

    if (selected.length === 2) {
      moves++;
      if (selected[0].value === selected[1].value) {
        selected[0].matched = true;
        selected[1].matched = true;
      }
      setTimeout(() => (selected = []), 1000);
    }
  }
  resetGame(); // Initialize the game on load
  
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

<!--List of my website projects -->
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


<!-- List of my education -->
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
  </section>


  <!-- List of my scientific publicaitons -->
  <section id="publications" class="py-20 flex flex-col gap-20">
    <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
      <h2 class="font-semibold text-3xl sm:text-4xl md:text-6xl text-center">My <span class="poppins text-violet-400">Publications</span></h2>
    </div>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      <Publications publications={publications[0]}> 
         <p> Benjamin J.E. Martin, Julie Brind’Amour, Kristoffer N. Jensen†, <span class="text-violet-400 poppins">Anastasia Kuzmin</span>, Zhen Cheng Liu, Matthew Lorincz and LeAnn J. Howe.</p>
      </Publications>
      <Publications publications={publications[1]}>
        <p>Jasmine Ono, <span class="text-violet-400 poppins">Anastasia Kuzmin</span>, Lesley Miller, Sarah P Otto</p>
      </Publications>
      <Publications publications={publications[2]}>
        <p>Aleeza C Gerstein, Jasmine Ono, Dara S Lo, Marcus L Campbell, <span class="text-violet-400 poppins">Anastasia Kuzmin</span>, Sarah P Otto</p>
      </Publications>
      <Publications publications={publications[3]}>
        <p>A. C. Gerstein, <span class="text-violet-400 poppins">A. Kuzmin</span>, & S. P. Otto</p>
      </Publications>
      <Publications publications={publications[4]}>
        <p><span class="text-violet-400 poppins">Anastasia Kuzmin</span>, Keith Jarvi, Kirk Lo, Leia Spencer, Gary YC Chow, Graham Macleod, Qianwei Wang, Susannah Varmuza</p>
      </Publications>
      <Publications publications={publications[5]}>
        <p><span class="text-violet-400 poppins">Anastasia Kuzmin</span>, Zhiming Han, Michael C. Golding, Mellissa R.W. Mann, Keith E. Latham, and Susannah Varmuza1</p>
      </Publications>
    </div>
  </section>


<!-- Games starting with match game -->
  <section>
    <div class="flex flex-col items-center justify-center h-screen bg-gray-900 text-white">
      <h1 class="text-3xl font-bold mb-4">Match Game</h1>
      <p class="mb-4">Moves: {moves}</p>
      <div class="grid grid-cols-4 gap-4">
        {#each cards as card}
          <button
            class="w-16 h-16 flex items-center justify-center text-2xl bg-gray-700 rounded-lg shadow-md transition-transform"
            on:click={() => selectCard(card)}
            class:selected={selected.includes(card) || card.matched}
          >
            {#if selected.includes(card) || card.matched}
              {card.value}
            {:else}
              ❓
            {/if}
          </button>
        {/each}
      </div>
    </div>
    <button
    on:click={resetGame}
    class="mt-6 px-4 py-2 bg-blue-500 hover:bg-blue-700 text-white font-bold rounded"
  >
    Reset Game
  </button>
    <style>
      .selected {
        background-color: #38bdf8;
      }
    </style>
  </section>
</main>






  <!-- <div class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full">
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
  </div> -->
  <!-- <p class="mx-auto">So why not invest?</p> -->