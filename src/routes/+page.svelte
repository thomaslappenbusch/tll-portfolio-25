<script lang="ts">
    import { goto } from "$app/navigation";
    import { ArrowRight, ChevronDown, ChevronLeft, ChevronRight, CircleHelp, ExternalLink, ExternalLinkIcon, Film, House } from "lucide-svelte";
    import Moon from "lucide-svelte/icons/moon";
    import Sun from "lucide-svelte/icons/sun";

    import { ModeWatcher, mode, toggleMode } from "mode-watcher";
    import { fade } from "svelte/transition";

    let currentSlide = $state(0)
    let p1Open = $state(false)
    let p2Open = $state(false)
    
</script>

<ModeWatcher defaultMode={"dark"}/>

<div class="flex items-center justify-between">
    <div class="flex flex-col">
        <p class="text-tertiary text-sm">Hello, my name is</p>
        <p class="qtext-content text-3xl sm:text-4xl xl:text-5xl font-medium">Thomas Lappenbusch</p>
        <div class="flex items-center justify-start space-x-3 sm:space-x-4 mt-3 flex-wrap">
            
       
            <button 
                onclick={() => window.open('https://discordapp.com/users/217831307219042304', '_blank')}
                class="text-sm cursor-pointer flex items-center text-indigo-400"
            >
                Discord
            </button>
            <button 
                onclick={() => window.open('https://www.linkedin.com/in/thomaslappenbusch/', '_blank')}
                class="text-sm  cursor-pointer flex items-center text-blue-400"
            >
                LinkedIn
            </button>
            <button 
                onclick={() => window.open('https://x.com/thomaslappenbus', '_blank')}
                class="text-sm  cursor-pointer flex items-center not-dark:text-black text-zinc-300"
            >
                Twitter / X
            </button>
            <button 
                onclick={() => window.open('https://x.com/thomaslappenbus', '_blank')}
                class="text-sm  cursor-pointer flex items-center text-[#14A800]"
            >
                Upwork
            </button>
            <div class="h-4 w-[1px] bg-tertiary/20  sm:hidden">
            </div>
            <button onclick={toggleMode} class="hover:bg-tertiary/20 transition cursor-pointer sm:hidden rounded-md h-8 w-8 p-1">
                {#if mode.current === "dark"}
                    <Moon class="h-full w-full"/>
                {:else}
                    <Sun class="h-full w-full p-[1px]"/>
                {/if}
            </button>
        </div>
    </div>
    <div class="hidden sm:flex items-center space-x-4 z-10">
        <!-- svelte-ignore a11y_consider_explicit_label -->
        <!-- <button class="h-6 w-6 text-content hover:text-accent transition cursor-pointer rounded-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16"><path fill="currentColor" d="M8 0c4.42 0 8 3.58 8 8a8.01 8.01 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38c0-.27.01-1.13.01-2.2c0-.75-.25-1.23-.54-1.48c1.78-.2 3.65-.88 3.65-3.95c0-.88-.31-1.59-.82-2.15c.08-.2.36-1.02-.08-2.12c0 0-.67-.22-2.2.82c-.64-.18-1.32-.27-2-.27s-1.36.09-2 .27c-1.53-1.03-2.2-.82-2.2-.82c-.44 1.1-.16 1.92-.08 2.12c-.51.56-.82 1.28-.82 2.15c0 3.06 1.86 3.75 3.64 3.95c-.23.2-.44.55-.51 1.07c-.46.21-1.61.55-2.33-.66c-.15-.24-.6-.83-1.23-.82c-.67.01-.27.38.01.53c.34.19.73.9.82 1.13c.16.45.68 1.31 2.69.94c0 .67.01 1.3.01 1.49c0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8"/></svg>
        </button>
        <button class="h-6 w-6 text-content hover:text-accent transition cursor-pointer rounded-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="currentColor" d="M116 3H12a8.91 8.91 0 0 0-9 8.8v104.42a8.91 8.91 0 0 0 9 8.78h104a8.93 8.93 0 0 0 9-8.81V11.77A8.93 8.93 0 0 0 116 3M39.17 107H21.06V48.73h18.11zm-9-66.21a10.5 10.5 0 1 1 10.49-10.5a10.5 10.5 0 0 1-10.54 10.48zM107 107H88.89V78.65c0-6.75-.12-15.44-9.41-15.44s-10.87 7.36-10.87 15V107H50.53V48.73h17.36v8h.24c2.42-4.58 8.32-9.41 17.13-9.41C103.6 47.28 107 59.35 107 75z"/></svg>
        </button>
        <div class="h-5 bg-tertiary/60 w-[2px] rounded-full"></div> -->
        <button onclick={toggleMode} class="hover:bg-tertiary/20 scale-125 mt-5 transition cursor-pointer rounded-md h-8 w-8 p-1">
            {#if mode.current === "dark"}
                <Moon class="h-full w-full"/>
            {:else}
                <Sun class="h-full w-full p-[1px]"/>
            {/if}
        </button>
    </div>
</div>

<!-- <div class="sm:hidden items-center space-x-6 z-10 flex mt-12 sm:mt-16">
    <button onclick={toggleMode} class="hover:bg-tertiary/20 -ml-1 transition cursor-pointer rounded-md h-10 w-10 p-1">
        {#if mode.current === "dark"}
            <Moon class="h-full w-full"/>
        {:else}
            <Sun class="h-full w-full p-[1px]"/>
        {/if}
    </button>
</div> -->

<div class="my-8 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<div class="flex flex-col w-full">
    <!-- Coastal UI Project -->
    <div class="flex flex-col items-start">
        <div onclick={() => p1Open = !p1Open} class="flex items-center cursor-pointer transition rounded-md justify-between grow w-full">
            <div class="flex flex-col">
                <div class="text-xl tracking-tight font-medium flex items-center">
                    Coastal UI
                    <a href="https://www.coastalui.com" target="_blank" class="hidden sm:flex ml-1 items-center cursor-pointer group hover:bg-tertiary/10 p-1 rounded-md relative w-6.5">
                        <div class="absolute bottom-8 rounded-md border border-tertiary/30 left-1/2 -translate-x-1/2 whitespace-nowrap px-2 py-1 text-center text-xs opacity-0 bg-background group-hover:opacity-100 pointer-events-none transition">
                            Open Website
                        </div>
                        <ExternalLinkIcon strokeWidth={1.5} class="h-5 w-5"/>
                    </a>
                </div>
                <p class="text-content/80 sm:text-md text-sm mt-1">A library of modern, dark UI elements for Tailwind CSS + Svelte. Over 4,000 unique visitors from Reddit and madewithsvelte.</p>
            </div>
            <div class={`ml-4 ${p1Open ? "rotate-180" : ""}`}>
                <ChevronDown strokeWidth={1.5} />
            </div>
        </div>
        {#if p1Open}
            <!-- Desktop Grid -->
            <div class="hidden sm:grid grid-cols-7 grid-rows-2 w-full mt-5 gap-1 h-[340px]">
                <img src="coastal1.png" class="row-span-2 col-span-5 rounded-md border border-secondary-muted/20 h-full object-cover"/>
                <img src="coastal2.png" class="row-span-1 col-span-2 rounded-md object-cover border border-secondary-muted/20 h-full"/>
                <img src="coastal2.png" class="row-span-1 col-span-2 rounded-md object-cover border border-secondary-muted/20 h-full"/>
            </div>
            <!-- Mobile Single Image -->
            <div class="sm:hidden mt-5">
                <img src="coastal1.png" class="w-full rounded-md border border-secondary-muted/20 object-cover"/>
                <a href="https://www.coastalui.com" target="_blank" class="w-full bg-content rounded-md mt-3 flex items-center justify-center text-background py-3">
                    Open Live Website
                    <ExternalLink class="h-4 w-4 ml-2"/>
                </a>
            </div>
        {/if}
    </div>

    <!-- Clutch Maps Project -->
    <div class="flex flex-col items-start mt-12">
        <div onclick={() => p2Open = !p2Open} class="flex items-center cursor-pointer transition rounded-md justify-between grow w-full">
            <div class="flex flex-col">
                <div class="text-xl tracking-tight font-medium flex items-center">
                    Clutch Maps
                    <a href="https://www.clutchmaps.com" target="_blank" class="hidden sm:flex ml-1 items-center cursor-pointer group hover:bg-tertiary/10 p-1 rounded-md relative w-6.5">
                        <div class="absolute bottom-8 rounded-md border border-tertiary/30 left-1/2 -translate-x-1/2 whitespace-nowrap px-2 py-1 text-center text-xs opacity-0 bg-background group-hover:opacity-100 pointer-events-none transition">
                            Open Website
                        </div>
                        <ExternalLinkIcon strokeWidth={1.5} class="h-5 w-5"/>
                    </a>
                </div>
                <p class="text-content/80 mt-1 sm:text-md text-sm">A web app for finding great driving routes near you. Currently built with Svelte + Mapbox, but currently in open beta.</p>
            </div>
            <div class={`ml-4 ${p2Open ? "rotate-180" : ""}`}>
                <ChevronDown strokeWidth={1.5} />
            </div>
        </div>
        {#if p2Open}
            <!-- Desktop Grid -->
            <div class="hidden sm:grid grid-cols-7 grid-rows-2 w-full mt-5 gap-1 h-[370px]">
                <img src="clutch1.png" class="row-span-2 col-span-5 rounded-md border border-secondary-muted/30 h-full object-cover"/>
                <img src="clutch2.png" class="row-span-1 col-span-2 rounded-md object-cover border border-secondary-muted/30 h-full"/>
                <img src="clutch3.png" class="row-span-1 col-span-2 rounded-md object-cover border border-secondary-muted/30 h-full"/>
            </div>
            <!-- Mobile Single Image -->
            <div class="sm:hidden mt-5">
                <img src="clutch1.png" class="w-full rounded-md border border-secondary-muted/30 object-cover"/>
                <a href="https://www.clutchmaps.com" target="_blank" class="w-full bg-content rounded-md mt-3 flex items-center justify-center text-background py-3">
                    Open Live Website
                    <ExternalLink class="h-4 w-4 ml-2"/>
                </a>
            </div>
        {/if}
    </div>
</div>


<div class="mt-12 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<div class="flex flex-col w-full">
    <div class="flex justify-between items-center my-12">
        <div class="text-sm font-medium text-tertiary">
            Freelance
        </div>
        <div class="text-sm text-[#14A800] hover:text-blue-600 cursor-pointer underline flex items-center">
            Hire me on Upwork
            <ExternalLinkIcon class="h-4 w-4 ml-1"/>
        </div>
    </div>
    <div class="grid grid-cols-1 gap-10 divide-dotted">
        <div class="flex items-center justify-between">
            <img src="virlofav.png" class="sm:h-7 sm:w-7 h-9 w-9 mr-2 bg-pink-200 dark:bg-pink-300 p-[5px] rounded-md"/>
            <div class="flex flex-col sm:hidden mr-auto">
                <a href="https://virlo.ai" target="_blank" rel="noopener noreferrer" class="text-lg flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                    Virlo.ai
                </a>
                <div class="text-xs italic tracking-tight mr-auto text-secondary">MVP Development (Svelte, Supabase)</div>
            </div>
            <a href="https://virlo.ai" target="_blank" rel="noopener noreferrer" class="text-lg hidden sm:flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                Virlo.ai
            </a>
            <div class="text-xs italic tracking-tight ml-auto hidden sm:flex">MVP Development (Svelte, Supabase)</div>
            <a href="https://virlo.ai" target="_blank" rel="noopener noreferrer" class="px-3 py-1 text-sm bg-muted/40 rounded-full sm:hidden">
                Open
            </a>
        </div>
        
        <div class="flex items-center justify-between">
            <img src="creatorcontactfav.png" class="sm:h-7 sm:w-7 h-9 w-9 mr-2 bg-zinc-300 p-[3px] rounded-md"/>
            <div class="flex flex-col sm:hidden mr-auto">
                <a href="https://creatorcontact.io" target="_blank" rel="noopener noreferrer" class="text-lg flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                    CreatorContact.io
                </a>
                <div class="text-xs italic mr-auto text-secondary">Onboarding Flow (Svelte)</div>
            </div>
            <a href="https://creatorcontact.io" target="_blank" rel="noopener noreferrer" class="text-lg hidden sm:flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                CreatorContact.io
            </a>
            <div class="text-xs italic ml-auto hidden sm:flex">Onboarding Flow (Svelte)</div>
            <a href="https://creatorcontact.io" target="_blank" rel="noopener noreferrer" class="px-3 py-1 text-sm bg-muted/40 rounded-full sm:hidden">
                Open
            </a>
        </div>
        
        <div class="flex items-center justify-between">
            <img src="socialplugfav.png" class="sm:h-7 sm:w-7 h-9 w-9 mr-2 bg-green-200 dark:bg-green-700 p-[4px] rounded-md"/>
            <div class="flex flex-col sm:hidden mr-auto">
                <a href="https://socialplug.io" target="_blank" rel="noopener noreferrer" class="text-lg flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                    SocialPlug.io
                </a>
                <div class="text-xs italic mr-auto text-secondary">JavaScript Consulting</div>
            </div>
            <a href="https://socialplug.io" target="_blank" rel="noopener noreferrer" class="text-lg hidden sm:flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                SocialPlug.io
            </a>
            <div class="text-xs italic ml-auto hidden sm:flex">JavaScript Consulting</div>
            <a href="https://socialplug.io" target="_blank" rel="noopener noreferrer" class="px-3 py-1 text-sm bg-muted/40 rounded-full sm:hidden">
                Open
            </a>
        </div>

        <div class="flex items-center justify-between">
                <img src="coderprepfav.png" class="sm:h-7 dark:border border-zinc-700 sm:w-7 h-9 w-9 mr-2 bg-slate-200 dark:bg-slate-700 rounded-md invert dark:invert-0"/>            <div class="flex flex-col sm:hidden mr-auto">
                <a href="https://coderprep.com" target="_blank" rel="noopener noreferrer" class="text-lg flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                    CoderPrep.com
                </a>
                <div class="text-xs italic mr-auto text-secondary">Frontend Development (Svelte, Tailwind)</div>
            </div>
            <a href="https://coderprep.com" target="_blank" rel="noopener noreferrer" class="text-lg hidden sm:flex items-center shrink-0 pr-8 hover:underline underline-offset-2 cursor-pointer hover:text-blue-600">
                CoderPrep.com
            </a>
            <div class="text-xs italic ml-auto hidden sm:flex">Frontend Development (Svelte, Tailwind)</div>
            <a href="https://coderprep.com" target="_blank" rel="noopener noreferrer" class="px-3 py-1 text-sm bg-muted/40 rounded-full sm:hidden">
                Open
            </a>
        </div>
        
        <div class="flex items-center justify-between">
            <svg class="sm:h-7 sm:w-7 h-9 w-9 mr-2  bg-green-100 dark:border-zinc-700 text-green-400 dark:text-green-600 dark:bg-zinc-800 p-[2px] rounded-md" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M266 51.727c-39.32 0-71 31.68-71 71s31.68 71.002 71 71.002s71-31.683 71-71.002c0-39.32-31.68-71-71-71m-144 32c-30.483 0-55 24.517-55 55c0 30.482 24.517 55.002 55 55.002s55-24.52 55-55.002s-24.517-55-55-55m-23 128v110.002h238V211.727zm350 4.648l-94 40.285v20.133l94 40.285zm-386 2.352v32h18v-32zm113 121.002v17.998h13.012l-51.123 136.275h19.222l51.507-136.275l.382 136.275h18l.382-136.275l51.507 136.275h19.222l-51.123-136.275H260v-17.998c-28.003-.003-55.997 0-84 0"/></svg>
            <div class="flex flex-col sm:hidden mr-auto">
                <a href="https://owlist.com" target="_blank" rel="noopener noreferrer" class="text-lg group flex items-center shrink-0 pr-8 cursor-pointer hover:text-blue-600">
                    <span class="group-hover:underline underline-offset-2">Owlist.com</span>
                    <span class="ml-1 italic text-tertiary text-xs mt-1">In Progress</span>
                </a>
                <div class="text-xs italic ml-auto text-secondary">MVP Development (Svelte, Supabase)</div>
            </div>
            <a href="https://owlist.com" target="_blank" rel="noopener noreferrer" class="text-lg group hidden sm:flex items-center shrink-0 pr-8 cursor-pointer hover:text-blue-600">
                <span class="group-hover:underline underline-offset-2">Owlist.com</span>
                <span class="ml-1 italic text-tertiary text-xs mt-1">In Progress</span>
            </a>
            <div class="text-xs italic ml-auto hidden sm:flex">MVP Development (Svelte, Supabase)</div>
             <a href="https://owlist.com" target="_blank" rel="noopener noreferrer" class="px-3 py-1 text-sm bg-muted/40 rounded-full sm:hidden">
                Open
            </a>
        </div>
    </div>
</div>

<div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div>


<div class="flex flex-col w-full">
    <div class="flex justify-between items-center mt-12">
        <div class="text-sm font-medium text-tertiary">
            Skillset
        </div>

    </div>
    <div class="flex items-center gap-y-2 space-x-2 flex-wrap mt-12">
        <div class="dark:bg-muted/20 bg-muted/10 text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            Svelte
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M10.99 1.974c2.92-1.86 6.957-.992 9.001 1.934a6.27 6.27 0 0 1 1.072 4.74a5.9 5.9 0 0 1-.88 2.198c.64 1.221.855 2.62.61 3.977a5.88 5.88 0 0 1-2.657 3.94l-5.127 3.268c-2.92 1.86-6.957.993-9.002-1.933a6.27 6.27 0 0 1-1.07-4.741a5.9 5.9 0 0 1 .88-2.198a6.2 6.2 0 0 1-.611-3.977a5.88 5.88 0 0 1 2.658-3.94zM8.049 20.25c.782.29 1.633.332 2.44.123c.369-.099.72-.253 1.042-.458l5.128-3.267a3.54 3.54 0 0 0 1.598-2.37a3.77 3.77 0 0 0-.645-2.85a4.07 4.07 0 0 0-4.37-1.62c-.369.099-.72.253-1.042.458l-1.957 1.246a1.1 1.1 0 0 1-.314.138a1.227 1.227 0 0 1-1.5-.899a1.1 1.1 0 0 1-.01-.45a1.07 1.07 0 0 1 .48-.713l5.129-3.268a1.1 1.1 0 0 1 .314-.138a1.23 1.23 0 0 1 1.317.489c.157.222.23.492.207.762l-.018.19l.191.058a6.6 6.6 0 0 1 2.005 1.003l.263.192l.096-.295q.078-.235.123-.478a3.77 3.77 0 0 0-.644-2.85a4.07 4.07 0 0 0-4.371-1.621a3.7 3.7 0 0 0-1.042.458L7.34 7.357a3.54 3.54 0 0 0-1.6 2.37a3.77 3.77 0 0 0 .645 2.85a4.07 4.07 0 0 0 4.371 1.62c.369-.099.72-.253 1.042-.457l1.956-1.248q.148-.093.315-.137a1.23 1.23 0 0 1 1.5.899c.034.147.037.3.011.449a1.07 1.07 0 0 1-.482.713l-5.127 3.269a1.1 1.1 0 0 1-.314.137a1.23 1.23 0 0 1-1.317-.488a1.15 1.15 0 0 1-.207-.762l.017-.19l-.19-.058a6.6 6.6 0 0 1-2.005-1.003l-.263-.192l-.096.295a4 4 0 0 0-.123.478a3.77 3.77 0 0 0 .644 2.85a4.07 4.07 0 0 0 1.93 1.498"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10 text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            React
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M12 10.11c1.03 0 1.87.84 1.87 1.89c0 1-.84 1.85-1.87 1.85S10.13 13 10.13 12c0-1.05.84-1.89 1.87-1.89M7.37 20c.63.38 2.01-.2 3.6-1.7c-.52-.59-1.03-1.23-1.51-1.9a23 23 0 0 1-2.4-.36c-.51 2.14-.32 3.61.31 3.96m.71-5.74l-.29-.51c-.11.29-.22.58-.29.86c.27.06.57.11.88.16zm6.54-.76l.81-1.5l-.81-1.5c-.3-.53-.62-1-.91-1.47C13.17 9 12.6 9 12 9s-1.17 0-1.71.03c-.29.47-.61.94-.91 1.47L8.57 12l.81 1.5c.3.53.62 1 .91 1.47c.54.03 1.11.03 1.71.03s1.17 0 1.71-.03c.29-.47.61-.94.91-1.47M12 6.78c-.19.22-.39.45-.59.72h1.18c-.2-.27-.4-.5-.59-.72m0 10.44c.19-.22.39-.45.59-.72h-1.18c.2.27.4.5.59.72M16.62 4c-.62-.38-2 .2-3.59 1.7c.52.59 1.03 1.23 1.51 1.9c.82.08 1.63.2 2.4.36c.51-2.14.32-3.61-.32-3.96m-.7 5.74l.29.51c.11-.29.22-.58.29-.86c-.27-.06-.57-.11-.88-.16zm1.45-7.05c1.47.84 1.63 3.05 1.01 5.63c2.54.75 4.37 1.99 4.37 3.68s-1.83 2.93-4.37 3.68c.62 2.58.46 4.79-1.01 5.63c-1.46.84-3.45-.12-5.37-1.95c-1.92 1.83-3.91 2.79-5.38 1.95c-1.46-.84-1.62-3.05-1-5.63c-2.54-.75-4.37-1.99-4.37-3.68s1.83-2.93 4.37-3.68c-.62-2.58-.46-4.79 1-5.63c1.47-.84 3.46.12 5.38 1.95c1.92-1.83 3.91-2.79 5.37-1.95M17.08 12c.34.75.64 1.5.89 2.26c2.1-.63 3.28-1.53 3.28-2.26s-1.18-1.63-3.28-2.26c-.25.76-.55 1.51-.89 2.26M6.92 12c-.34-.75-.64-1.5-.89-2.26c-2.1.63-3.28 1.53-3.28 2.26s1.18 1.63 3.28 2.26c.25-.76.55-1.51.89-2.26m9 2.26l-.3.51c.31-.05.61-.1.88-.16c-.07-.28-.18-.57-.29-.86zm-2.89 4.04c1.59 1.5 2.97 2.08 3.59 1.7c.64-.35.83-1.82.32-3.96c-.77.16-1.58.28-2.4.36c-.48.67-.99 1.31-1.51 1.9M8.08 9.74l.3-.51c-.31.05-.61.1-.88.16c.07.28.18.57.29.86zm2.89-4.04C9.38 4.2 8 3.62 7.37 4c-.63.35-.82 1.82-.31 3.96a23 23 0 0 1 2.4-.36c.48-.67.99-1.31 1.51-1.9"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10  text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            Tailwind
            <svg class="inline-block ml-1.5 sm:ml-2 h-4 w-4 sm:h-5 sm:w-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M12 6c-2.67 0-4.33 1.33-5 4c1-1.33 2.17-1.83 3.5-1.5c.76.19 1.31.74 1.91 1.35c.98 1 2.09 2.15 4.59 2.15c2.67 0 4.33-1.33 5-4c-1 1.33-2.17 1.83-3.5 1.5c-.76-.19-1.3-.74-1.91-1.35C15.61 7.15 14.5 6 12 6m-5 6c-2.67 0-4.33 1.33-5 4c1-1.33 2.17-1.83 3.5-1.5c.76.19 1.3.74 1.91 1.35C8.39 16.85 9.5 18 12 18c2.67 0 4.33-1.33 5-4c-1 1.33-2.17 1.83-3.5 1.5c-.76-.19-1.3-.74-1.91-1.35C10.61 13.15 9.5 12 7 12"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10  text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            TypeScript
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><g fill="none"><g clip-path="url(#akarIconsTypescriptFill0)"><path fill="currentColor" d="M23.429 0H.57A.57.57 0 0 0 0 .571V23.43a.57.57 0 0 0 .571.571H23.43a.57.57 0 0 0 .571-.571V.57a.57.57 0 0 0-.572-.57m-9.143 12.826h-2.857v8.888H9.143v-8.888H6.286v-1.969h8zm.64 8.38v-2.375s1.298.978 2.855.978s1.497-1.018 1.497-1.158c0-1.477-4.412-1.477-4.412-4.751c0-4.452 6.429-2.695 6.429-2.695l-.08 2.116s-1.078-.719-2.296-.719s-1.657.58-1.657 1.198c0 1.597 4.452 1.438 4.452 4.652c0 4.95-6.788 2.755-6.788 2.755"/></g><defs><clipPath id="akarIconsTypescriptFill0"><path fill="#fff" d="M0 0h24v24H0z"/></clipPath></defs></g></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10  text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            JavaScript
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32"><path fill="currentColor" d="M0 0h32v32H0zm29.38 24.37c-.234-1.464-1.188-2.688-4.005-3.833c-.979-.458-2.073-.781-2.396-1.521c-.12-.438-.141-.677-.063-.938c.203-.865 1.219-1.12 2.021-.88c.521.161 1 .557 1.302 1.198c1.38-.901 1.38-.901 2.339-1.5c-.359-.557-.536-.802-.781-1.036c-.839-.943-1.958-1.422-3.776-1.38l-.943.12c-.901.219-1.76.698-2.281 1.339c-1.516 1.719-1.078 4.719.76 5.964c1.818 1.359 4.479 1.656 4.823 2.938c.318 1.563-1.161 2.063-2.625 1.88c-1.078-.24-1.677-.781-2.339-1.781l-2.438 1.401c.276.641.599.917 1.078 1.479c2.318 2.339 8.12 2.219 9.161-1.339c.036-.12.318-.943.099-2.198zm-11.979-9.662h-2.995c0 2.583-.016 5.151-.016 7.74c0 1.641.083 3.151-.182 3.615c-.443.917-1.573.802-2.089.641c-.526-.26-.797-.62-1.104-1.141c-.089-.141-.151-.26-.172-.26l-2.432 1.5c.406.839 1 1.563 1.766 2.021c1.141.682 2.672.901 4.276.542c1.042-.302 1.943-.922 2.411-1.88c.682-1.24.536-2.76.531-4.464c.016-2.74 0-5.479 0-8.24z"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10 text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            Supabase
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4 sm:w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M3.084 15.25c-1.664 0-2.6-1.912-1.58-3.226L10.21.806C10.794.054 12 .466 12 1.42v7.33h8.916c1.663 0 2.6 1.912 1.58 3.226L13.79 23.194c-.584.752-1.79.34-1.79-.613V15.25z"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10  text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            Mapbox.js
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M12 2a10 10 0 0 1 10 10a10 10 0 0 1-10 10A10 10 0 0 1 2 12A10 10 0 0 1 12 2m4.75 12.45c1.9-1.9 1.83-5.06-.16-7.04s-5.14-2.06-7.04-.16c-3.43 3.43-2.33 9.53-2.33 9.53s6.11 1.09 9.53-2.33m-3.6-6.59l.98 2.01l2.01.98l-2.01.98l-.98 2.01l-.98-2.01l-2.01-.98l2.01-.98z"/></svg>
        </div>
        <div class="dark:bg-muted/20 bg-muted/10 text-sm sm:text-base h-8 px-2 sm:px-3 sm:py-2 sm:h-auto rounded-sm flex items-center select-none">
            Three.js
            <svg class="inline-block ml-1.5 sm:ml-2 h-3.5 w-3.5 sm:h-4.5 sm:w-4.5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M.38 0a.268.268 0 0 0-.256.332l2.894 11.716l.01.04l2.89 11.708a.268.268 0 0 0 .447.128L23.802 7.15a.268.268 0 0 0-.112-.45l-5.784-1.667a.3.3 0 0 0-.123-.035L6.38 1.715a.27.27 0 0 0-.144-.04L.456.01A.3.3 0 0 0 .38 0m.374.654L5.71 2.08L1.99 5.664zM6.61 2.34l4.864 1.4l-3.65 3.515zm-.522.12l1.217 4.926l-4.877-1.4zm6.28 1.538l4.878 1.404l-3.662 3.53zm-.52.13l1.208 4.9l-4.853-1.392zm6.3 1.534l4.947 1.424l-3.715 3.574zm-.524.12l1.215 4.926l-4.876-1.398zm-15.432.696l4.964 1.424l-3.726 3.586zM8.047 8.15l4.877 1.4l-3.66 3.527zm-.518.137l1.236 5.017l-4.963-1.432zm6.274 1.535l4.965 1.425l-3.73 3.586zm-.52.127l1.235 5.012l-4.958-1.43zm-9.63 2.438l4.873 1.406l-3.656 3.523zm5.854 1.687l4.863 1.403l-3.648 3.51zm-.54.04l1.214 4.927l-4.875-1.4zm-3.896 4.02l5.037 1.442l-3.782 3.638z"/></svg>
        </div>
    </div>
</div>

<div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<!-- <div class="flex flex-col w-full">
    <div class="flex justify-between items-center mt-12">
        <div class="text-2xl">
            Image Gallery
        </div>
    </div>
    <div class="w-full h-[700px] mt-12 sm:grid grid-cols-2 grid-rows-12 gap-2 hidden">
        <div class="col-span-1 row-span-5 bg-zinc-50 rounded-sm relative overflow-hidden object-cover">
            <img src="gallery2.jpg" class="inset-0 absolute scale-140"/>
        </div>
        <div class="col-span-1 row-span-8 bg-zinc-50 rounded-sm relative overflow-hidden">
            <img src="https://cdn.discordapp.com/attachments/380941291338596353/1375333972284014612/image.jpg?ex=68314f13&is=682ffd93&hm=45f4f06e979338944894bff73ae52e3a4096a850244f130b61530bff690ed00c&" class="inset-0 absolute object-cover"/>
        </div>
        <div class="col-span-1 row-span-8 bg-zinc-50 rounded-sm relative overflow-hidden object-cover">
            <img src="https://pbs.twimg.com/media/GrjEShfboAARzIG?format=jpg&name=small" class="inset-0 absolute object-cover"/>
        </div>
        <div class="col-span-1 row-span-5 border border-zinc-200 rounded-sm relative overflow-hidden">
            <img src="coastalui.png" class="inset-0 absolute my-auto"/>
        </div>
    </div>
</div> -->

<!-- <div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div> -->

<!-- <div class="flex flex-col w-full">
    <div class="flex justify-between items-center mt-12">
        <div class="text-2xl">
            Development Gallery
        </div>
    </div>
    <p class="mb-12 mt-3 text-tertiary">All of these were made by me. Get a hands-on feel for my style and capabilities.</p>
    <div class="w-full relative h-[400px] bg-gradient-to-b to-muted/2 overflow-hidden from-muted/5 border-2 border-muted/30 border-y-muted/20 rounded-md">
        <div class="absolute inset-0 w-[200%] h-full flex items-center transition duration-700 ease-in-out" style={`transform: translateX(-${currentSlide * 50}%)`}>
            <div class="w-1/2 bg-gradient-to-r h-full flex-shrink-0 flex items-center justify-center relative">
                <div class="absolute top-2 left-2 italic text-xs text-tertiary">
                    Info Card from <span class="underline">Clutch Maps</span>
                </div>
                <div class="flex flex-col w-[80vw] sm:w-[430px] relative ">
                    <div class="bg-tertiary/10 rounded-md grow flex items-center font-sans z-30">
                        <a
                            class="relative h-[150px] hidden sm:flex sm:w-[150px] overflow-hidden rounded-l-md bg-content/50 group"
                        >
                            <img 
                                src="https://media.istockphoto.com/id/480155792/photo/fogged-in.jpg?s=612x612&w=0&k=20&c=f7eqdlimc3B9pxkO6Gd6yZEgVNNTFNw0LhUj3s04_Sg="
                                class="absolute inset-0 h-full w-full z-10 object-cover transition-transform duration-300 hover:scale-105"
                            />
                        </a>
                        <div class="flex flex-col px-3 rounded-r-md grow h-[145px] py-2">
                            <div class="font-medium text-base text-content flex items-center justify-between">
                                Lake Cushman Drive
                            </div>
                            <div class="text-tertiary text-[11px] -mt-[2px]">Western Washington • 50 minutes • 43 miles</div>
                            <div class="flex items-center mt-auto w-full space-x-2">
                                <div class="relative group grow">
                                
                                    <a class="text-[11px] sm:text-[13px] focus:ring-0 h-8 flex items-center justify-center cursor-pointer text-content  py-[2px] rounded-md not-dark:bg-white/70 dark:bg-tertiary/20 border border-secondary/10">
                                        Open in Google Maps    
                                        <svg class="fill-content/80 ml-2 h-4.5 w-4.5" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 48 48"><path fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="M9.5 5.5a4 4 0 0 0-4 4v4.7l28.3 28.3h4.7a4 4 0 0 0 4-4v-29a4 4 0 0 0-4-4zm20.66 3.895a8.446 8.446 0 0 1 8.445 8.447v0c0 4.914-3.995 8.748-8.445 13.774c-4.262-4.812-8.104-8.533-8.423-13.154a8 8 0 0 1-.025-.62a8.446 8.446 0 0 1 8.445-8.448zm0 4.387a4.06 4.06 0 0 0-4.06 4.06v0a4.06 4.06 0 0 0 4.06 4.06h0a4.06 4.06 0 0 0 0-8.12M5.5 27.182V38.5a4 4 0 0 0 4 4h11.32z" stroke-width="1"/></svg>
                                    </a>
                                </div>
                            </div>
                        </div>
                        <a class="absolute top-2 right-2">
                            <svg class="text-content fill-background cursor-pointer" xmlns="http://www.w3.org/2000/svg" width="21" height="21" viewBox="0 0 24 24"><path fill="currentColor" d="M5 21V5q0-.825.588-1.412T7 3h10q.825 0 1.413.588T19 5v16l-7-3zm2-3.05l5-2.15l5 2.15V5H7zM7 5h10z"/></svg>
                        </a>
                    </div>
                    <div class="h-4 w-12 mx-auto z-0">
                    </div>
                </div>
            </div>
            <div class="w-1/2 bg-gradient-to-r h-full flex-shrink-0 flex flex-col space-y-8 items-center justify-center relative">
                <div class="absolute top-2 left-2 italic text-xs text-tertiary">
                    Buttons from <span class="underline">Coastal UI</span>
                </div>
                <button class="group px-5 py-2 bg-indigo-600 dark:bg-indigo-950 rounded-lg text-white relative cursor-pointer overflow-hidden">
                    <div class="absolute h-[300px] w-2 bg-indigo-200 blur-2xl -top-45 left-0 rotate-60 transition-all duration-[1300ms] group-hover:-top-32 group-hover:left-45"></div>
                    <span class="relative z-10 font-light">Get Started</span>
                </button>
                <button class="flex items-center justify-center border bg-zinc-600 border-zinc-700 text-content dark:border-zinc-600 rounded-full dark:bg-zinc-950 cursor-pointer">
                    <div class="border-r border-zinc-700 dark:border-zinc-600  pr-2 text-[#EEEEE4] py-1.5 pl-3 font-light text-sm">Join Newsletter</div>
                    <ChevronDown class="text-[#EEEEE4] w-4.5 h-4.5 ml-1 mr-1.5 rotate-270" strokeWidth={1.7}/>
                </button>
                <button class="group bg-gradient-to-b cursor-pointer from-[#538ee7] to-[#377fd6] text-zinc-200 flex items-center text-sm px-5 py-2 rounded-full relative overflow-hidden border border-[#1a3a6a] hover:border-[#2a4a7a] transition-colors duration-300">
                    <div class="absolute inset-0 bg-[#082550] translate-y-full group-hover:translate-y-0 transition-transform duration-500"></div>
                    <span class="relative z-10">Continue</span>
                    <ArrowRight class="relative z-10 w-4 h-4 ml-2 text-zinc-200 group-hover:translate-x-1 transition-all duration-500"/>
                </button>
            </div>
        </div>
        
        {#if currentSlide > 0}
            <button out:fade={{duration:100}} onclick={() => currentSlide = currentSlide - 1} class="cursor-pointer absolute left-2 bottom-0 sm:top-1/2 -translate-y-1/2 hover:bg-tertiary/10 sm:hover:bg-transparent rounded-full">
                <ChevronLeft class="h-7 w-7 pr-0.5"/>
            </button>
        {/if}
        
        {#if currentSlide < 1}
            <button out:fade={{duration:100}} onclick={() => currentSlide = currentSlide + 1} class="cursor-pointer absolute right-2 bottom-0 sm:top-1/2 -translate-y-1/2 hover:bg-tertiary/10 sm:hover:bg-transparent rounded-full">
                <ChevronRight class="h-7 w-7 pl-0.5"/>
            </button>
        {/if}
    </div>
</div> -->

<!-- <div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div> -->


<div class="flex items-center justify-center space-x-6 mt-12 w-full mb-[35vh]">
    Open blogs <span class="text-sm text-tertiary ml-2">Not availalbe yet</span>
</div>