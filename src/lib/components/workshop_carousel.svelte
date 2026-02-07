<script lang="ts">
    import { onMount } from 'svelte';
    import { fade, slide } from 'svelte/transition';
    
    const workshops = [
        {
            title: "BruinAI: Intro to API",
            image: "bruin-ai.png",
            description: "Welcome to AI API workshop hosted by BruinAI! We will walk you through everything you need to know about selecting and implementing AI APIs for different modalities, desired outputs, and latency requirements."
        },
        {
            title: "AIRES: AI Ethics & Safety",
            image: "aires.png",
            description: "The Artificial Intelligence Robotics Ethics Society (AIRES @ UCLA) educates future AI leaders and the broader UCLA population on the evolving impact of AI on society, ethics, and beyond. We're committed to the national AIRES mission, promoting transparent and ethical regulation, implementation, and implications of AI. Our club events include \"Tuesday Talks,\" which are informative discussions about the ethics of real-world AI applications (while having tea and biscuits!), Speaker Series with influential AI experts, workshops on AI tools/models, collaborations with graduate student organizations, and an annual Spring Conference with professors and industry professionals as panelists. Members can also lead quarterly research projects on topics of their choice, and join fun socials, such as getting boba in Westwood! We’ll be presenting on the failure modes in different AI chatbots, by going through a series of generative AIs and testing where each one fails. The goal is to see if you all can make the AI fail in some way to be aware of potential potholes if you choose to integrate an AI tool into your product. We’ll also be discussing how AI models can hallucinate and how to avoid hallucinations, like how AI models can “recognize” common visual illusions when there actually is not any illusion (or an illusion-illusion)."
        },
        {
            title: "ACM AI: Intro to Git",
            image: "acm-ai.png",
            description: "New to Git or need a quick refresh before hacking? ACM AI is hosting an Intro to Git workshop to help you learn the basics of version control, collaboration, and team workflows. We’ll cover how to use Git and GitHub to work smoothly with teammates, avoid merge conflicts, and move fast during hackathons like QWER Hacks! See you there :))"
        },
        {
            title: "Blueprint: Intro to UI/UX",
            image: "blueprint.png",
            description: "LA Blueprint is a student-run 501(c)(3) nonprofit committed to building and promoting tech for social good—free of charge. We collaborate with nonprofit organizations in Southern California and beyond to build mobile and web applications."
        },
        {
            title: "MLH: Intro to Git Copilot & Intro to Gemini",
            image: "mlh.png",
            description: "Hacking with GitHub Copilot: Elevate your hackathon game in just under an hour! Join this workshop on Hacking with GitHub Copilot, and discover how this AI companion transforms the coding experience for beginners and seasoned developers. Copilot isn't just another tool you can use to speed up your development; it's like having another hacker on your team!\nIntro to Google AI Studio: Google AI Studio is the fastest way to start building with the Gemini family of multimodal generative AI models. Google AI Studio allows you to try out Gemini's massive token context window, grab an API key in seconds, and so much more."
        }
    ];

    let currentIndex = 0;
    
    function next() {
        currentIndex = (currentIndex + 1) % workshops.length;
    }
    
    function prev() {
        currentIndex = (currentIndex - 1 + workshops.length) % workshops.length;
    }
</script>

<div class="w-full max-w-4xl mx-auto p-6 text-white">
    <h2 class="text-3xl md:text-5xl mb-8 text-center" style="font-family: 'Ranille Normal', serif; color: #FFFFFF; text-shadow: 0 0 30px rgba(197, 160, 89, 0.5);">
        Scheduled Workshops
    </h2>

    <div class="relative bg-black/40 backdrop-blur-md rounded-[40px] p-16 border border-white/10 min-h-[300px] flex flex-col justify-center shadow-lg">
        <!-- Navigation Buttons -->
        <button 
            class="absolute left-2 md:left-4 top-1/2 -translate-y-1/2 p-2 text-white/70 hover:text-[#C5A059] transition-colors z-10 bg-black/20 rounded-full hover:bg-black/40"
            on:click={prev}
            aria-label="Previous workshop"
        >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-6 h-6 md:w-8 md:h-8">
                <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
            </svg>
        </button>
        
        <button 
            class="absolute right-2 md:right-4 top-1/2 -translate-y-1/2 p-2 text-white/70 hover:text-[#C5A059] transition-colors z-10 bg-black/20 rounded-full hover:bg-black/40"
            on:click={next}
            aria-label="Next workshop"
        >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="w-6 h-6 md:w-8 md:h-8">
                <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
            </svg>
        </button>

        <!-- Content -->
        <div class="px-8 md:px-16 text-center">
            {#key currentIndex}
                <div in:fade={{ duration: 200, delay: 100 }} out:fade={{ duration: 100 }}>
                    <div class="flex justify-center mb-6">
                        <img 
                            src={workshops[currentIndex].image} 
                            alt="{workshops[currentIndex].title} logo" 
                            class="h-48 md:h-64 w-auto object-contain rounded-[40px] bg-white"
                        />
                    </div>
                    
                    <h3 class="text-xl md:text-3xl font-bold mb-4 text-[#C5A059] tracking-wide" style="font-family: 'Ranille Normal', serif;">
                        {workshops[currentIndex].title}
                    </h3>
                    <div class="max-h-[300px] overflow-y-auto pr-2 custom-scrollbar">
                        <div class="text-base md:text-lg leading-relaxed text-gray-200" style="font-family: 'Spectral', serif;">
                            {#each workshops[currentIndex].description.split('\n') as line, lineIndex}
                                {#if line.trim().length}
                                    <p class={lineIndex > 0 ? 'mt-3' : ''}>{line}</p>
                                {/if}
                            {/each}
                        </div>
                    </div>
                </div>
            {/key}
        </div>
        
        <!-- Indicators -->
        <div class="absolute bottom-4 left-1/2 -translate-x-1/2 flex gap-2 mt-4">
            {#each workshops as _, i}
                <button 
                    class="h-2 rounded-full transition-all duration-300 {i === currentIndex ? 'bg-[#C5A059] w-8' : 'bg-white/30 hover:bg-white/50 w-2'}"
                    on:click={() => currentIndex = i}
                    aria-label="Go to slide {i + 1}"
                ></button>
            {/each}
        </div>
    </div>
</div>

<style>
    /* Custom Scrollbar for overflow content */
    .custom-scrollbar::-webkit-scrollbar {
        width: 6px;
    }
    .custom-scrollbar::-webkit-scrollbar-track {
        background: rgba(255, 255, 255, 0.05);
        border-radius: 3px;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
        background: rgba(197, 160, 89, 0.5);
        border-radius: 3px;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb:hover {
        background: rgba(197, 160, 89, 0.8);
    }
</style>