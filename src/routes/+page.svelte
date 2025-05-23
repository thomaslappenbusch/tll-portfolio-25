<script lang="ts">
    import { ArrowRight, ChevronDown, ChevronLeft, ChevronRight, ExternalLinkIcon } from "lucide-svelte";
    import Moon from "lucide-svelte/icons/moon";
    import Sun from "lucide-svelte/icons/sun";

    import { ModeWatcher, mode, toggleMode } from "mode-watcher";
    import { fade } from "svelte/transition";

    let currentSlide = $state(0)
    
</script>

<div class="flex items-center justify-between">
    <div class="flex flex-col">
        <p class="text-tertiary text-sm">Hello, my name is</p>
        <p class="text-content text-3xl sm:text-4xl xl:text-5xl font-medium">Thomas Lappenbusch</p>
    </div>
    <div class="sm:flex items-center space-x-4 z-10 hidden">
        <!-- svelte-ignore a11y_consider_explicit_label -->
        <button class="h-6 w-6 text-content hover:text-accent transition cursor-pointer rounded-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16"><path fill="currentColor" d="M8 0c4.42 0 8 3.58 8 8a8.01 8.01 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38c0-.27.01-1.13.01-2.2c0-.75-.25-1.23-.54-1.48c1.78-.2 3.65-.88 3.65-3.95c0-.88-.31-1.59-.82-2.15c.08-.2.36-1.02-.08-2.12c0 0-.67-.22-2.2.82c-.64-.18-1.32-.27-2-.27s-1.36.09-2 .27c-1.53-1.03-2.2-.82-2.2-.82c-.44 1.1-.16 1.92-.08 2.12c-.51.56-.82 1.28-.82 2.15c0 3.06 1.86 3.75 3.64 3.95c-.23.2-.44.55-.51 1.07c-.46.21-1.61.55-2.33-.66c-.15-.24-.6-.83-1.23-.82c-.67.01-.27.38.01.53c.34.19.73.9.82 1.13c.16.45.68 1.31 2.69.94c0 .67.01 1.3.01 1.49c0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8"/></svg>
        </button>
        <!-- svelte-ignore a11y_consider_explicit_label -->
        <button class="h-6 w-6 text-content hover:text-accent transition cursor-pointer rounded-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="currentColor" d="M116 3H12a8.91 8.91 0 0 0-9 8.8v104.42a8.91 8.91 0 0 0 9 8.78h104a8.93 8.93 0 0 0 9-8.81V11.77A8.93 8.93 0 0 0 116 3M39.17 107H21.06V48.73h18.11zm-9-66.21a10.5 10.5 0 1 1 10.49-10.5a10.5 10.5 0 0 1-10.54 10.48zM107 107H88.89V78.65c0-6.75-.12-15.44-9.41-15.44s-10.87 7.36-10.87 15V107H50.53V48.73h17.36v8h.24c2.42-4.58 8.32-9.41 17.13-9.41C103.6 47.28 107 59.35 107 75z"/></svg>
        </button>
        <div class="h-5 bg-tertiary/60 w-[2px] rounded-full"></div>
        <button onclick={toggleMode} class="hover:bg-tertiary/20 transition cursor-pointer rounded-md h-8 w-8 p-1">
            {#if mode.current === "dark"}
                <Moon class="h-full w-full"/>
            {:else}
                <Sun class="h-full w-full p-[1px]"/>
            {/if}
        </button>
        
    </div>
</div>

<div class="sm:hidden items-center space-x-6 z-10 flex mt-12 sm:mt-16">
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a href="test" target="_blank" class="h-9 w-9 text-content hover:text-accent transition cursor-pointer rounded-md">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16"><path fill="currentColor" d="M8 0c4.42 0 8 3.58 8 8a8.01 8.01 0 0 1-5.45 7.59c-.4.08-.55-.17-.55-.38c0-.27.01-1.13.01-2.2c0-.75-.25-1.23-.54-1.48c1.78-.2 3.65-.88 3.65-3.95c0-.88-.31-1.59-.82-2.15c.08-.2.36-1.02-.08-2.12c0 0-.67-.22-2.2.82c-.64-.18-1.32-.27-2-.27s-1.36.09-2 .27c-1.53-1.03-2.2-.82-2.2-.82c-.44 1.1-.16 1.92-.08 2.12c-.51.56-.82 1.28-.82 2.15c0 3.06 1.86 3.75 3.64 3.95c-.23.2-.44.55-.51 1.07c-.46.21-1.61.55-2.33-.66c-.15-.24-.6-.83-1.23-.82c-.67.01-.27.38.01.53c.34.19.73.9.82 1.13c.16.45.68 1.31 2.69.94c0 .67.01 1.3.01 1.49c0 .21-.15.45-.55.38A7.995 7.995 0 0 1 0 8c0-4.42 3.58-8 8-8"/></svg>
    </a>
    <!-- svelte-ignore a11y_consider_explicit_label -->
    <a class="h-9 w-9 text-content hover:text-accent transition cursor-pointer rounded-md">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="currentColor" d="M116 3H12a8.91 8.91 0 0 0-9 8.8v104.42a8.91 8.91 0 0 0 9 8.78h104a8.93 8.93 0 0 0 9-8.81V11.77A8.93 8.93 0 0 0 116 3M39.17 107H21.06V48.73h18.11zm-9-66.21a10.5 10.5 0 1 1 10.49-10.5a10.5 10.5 0 0 1-10.54 10.48zM107 107H88.89V78.65c0-6.75-.12-15.44-9.41-15.44s-10.87 7.36-10.87 15V107H50.53V48.73h17.36v8h.24c2.42-4.58 8.32-9.41 17.13-9.41C103.6 47.28 107 59.35 107 75z"/></svg>
    </a>
    <div class="h-5 bg-tertiary/60 w-[2px] rounded-full"></div>
    <button onclick={toggleMode} class="hover:bg-tertiary/20 -ml-1 transition cursor-pointer rounded-md h-10 w-10 p-1">
        {#if mode.current === "dark"}
            <Moon class="h-full w-full"/>
        {:else}
            <Sun class="h-full w-full p-[1px]"/>
        {/if}
    </button>
</div>

<p class="text-start text-content mt-12 sm:mt-16 text-lg ">
    <!-- I'm a frontend developer, who specalizes in 
    <span class="text-[#ff3e00] font-medium">Svelte<svg class="h-4 w-4 inline-block ml-1 -mt-[2px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="#ff3e00" d="M110.43 16.936C98.553-.076 75.09-5.118 58.13 5.696l-29.792 19a34.2 34.2 0 0 0-15.48 22.897a25.478 30.64 0 0 0-.572 6.396a36.15 36.15 0 0 0 4.163 16.73A34.4 34.4 0 0 0 11.34 83.5a25.348 30.483 0 0 0 .345 14.412a36.5 36.5 0 0 0 5.9 13.152c11.878 17.01 35.394 22.053 52.3 11.24l29.762-19.001a34.13 34.13 0 0 0 15.438-22.918a35.5 35.5 0 0 0 .572-6.386a36.2 36.2 0 0 0-4.112-16.71a34.4 34.4 0 0 0 5.112-12.77c.369-2.11.557-4.245.562-6.386a36.4 36.4 0 0 0-6.787-21.178z"/><path fill="#fff" d="M55.219 112.662a28.463 34.23 0 0 1-5.954.76a23.64 23.64 0 0 1-19.435-10.187a21.9 21.9 0 0 1-4.08-12.74a15.658 18.83 0 0 1 .333-3.833a15.425 18.55 0 0 1 .72-2.782l.561-1.708l1.52 1.156a38.7 38.7 0 0 0 11.658 5.834l1.104.333l-.104 1.104v.573a6.63 6.63 0 0 0 1.228 3.854a7.1 7.1 0 0 0 2.538 2.288a8.262 9.936 0 0 0 3.312.837a8.251 9.923 0 0 0 1.79-.229a7.272 8.745 0 0 0 1.833-.802l29.76-19.094a6.26 6.26 0 0 0 2.904-5.302a6.62 6.62 0 0 0-1.26-3.844a7.14 7.14 0 0 0-2.553-2.252a8.313 9.997 0 0 0-3.307-.81a8.246 9.917 0 0 0-1.79.23a6.938 8.344 0 0 0-1.822.801l-11.346 7.25a24.376 29.314 0 0 1-6.048 2.656a23.64 23.64 0 0 1-25.39-9.416a21.94 21.94 0 0 1-4.08-12.74c.002-1.285.114-2.567.333-3.833a20.65 20.65 0 0 1 9.286-13.781l29.792-18.99a21.9 21.9 0 0 1 6.048-2.667a24 24 0 0 1 5.954-.75A23.68 23.68 0 0 1 98.22 24.745a21.94 21.94 0 0 1 4.029 12.75a15.748 18.939 0 0 1-.334 3.844a15.407 18.529 0 0 1-.718 2.781l-.562 1.708l-1.52-1.114a38.4 38.4 0 0 0-11.658-5.834l-1.104-.343l.104-1.105v-.572a6.7 6.7 0 0 0-1.228-3.865a7.1 7.1 0 0 0-2.55-2.25a8.309 9.992 0 0 0-3.3-.813a8.221 9.887 0 0 0-1.77.271a6.819 8.2 0 0 0-1.831.802l-29.793 18.99a5.88 7.071 0 0 0-1.836 1.79a4.75 5.713 0 0 0-.963 2.377a5.037 6.057 0 0 0-.136 1.104a6.62 6.62 0 0 0 1.228 3.844a7.1 7.1 0 0 0 2.549 2.25a8.299 9.98 0 0 0 3.301.812a8.247 9.918 0 0 0 1.79-.23a6.943 8.35 0 0 0 1.833-.801l11.367-7.292a24.218 29.125 0 0 1 6.048-2.656a28.526 34.305 0 0 1 5.954-.76A23.66 23.66 0 0 1 96.566 60.61a21.94 21.94 0 0 1 3.737 16.614a20.6 20.6 0 0 1-9.286 13.781l-29.74 18.99a24.308 29.233 0 0 1-6.057 2.667z"/></svg></span>, 
    
    <span class="text-[#38bdf8] font-medium">Tailwind<svg class="h-4 w-4 inline-block ml-1 -mt-[2px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="#38bdf8" d="M64.004 25.602c-17.067 0-27.73 8.53-32 25.597c6.398-8.531 13.867-11.73 22.398-9.597c4.871 1.214 8.352 4.746 12.207 8.66C72.883 56.629 80.145 64 96.004 64c17.066 0 27.73-8.531 32-25.602q-9.6 12.803-22.399 9.602c-4.87-1.215-8.347-4.746-12.207-8.66c-6.27-6.367-13.53-13.738-29.394-13.738M32.004 64c-17.066 0-27.73 8.531-32 25.602Q9.603 76.799 22.402 80c4.871 1.215 8.352 4.746 12.207 8.66c6.274 6.367 13.536 13.738 29.395 13.738c17.066 0 27.73-8.53 32-25.597q-9.6 12.797-22.399 9.597c-4.87-1.214-8.347-4.746-12.207-8.66C55.128 71.371 47.868 64 32.004 64m0 0"/></svg></span> and 
    
    <span class="text-[#007acc]">Typescript<svg class="h-4 w-4 inline-block ml-1 -mt-[2px]" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="#fff" d="M22.67 47h99.67v73.67H22.67z"/><path fill="#007acc" d="M1.5 63.91v62.5h125v-125H1.5zm100.73-5a15.56 15.56 0 0 1 7.82 4.5a20.6 20.6 0 0 1 3 4c0 .16-5.4 3.81-8.69 5.85c-.12.08-.6-.44-1.13-1.23a7.09 7.09 0 0 0-5.87-3.53c-3.79-.26-6.23 1.73-6.21 5a4.6 4.6 0 0 0 .54 2.34c.83 1.73 2.38 2.76 7.24 4.86c8.95 3.85 12.78 6.39 15.16 10c2.66 4 3.25 10.46 1.45 15.24c-2 5.2-6.9 8.73-13.83 9.9a38.3 38.3 0 0 1-9.52-.1a23 23 0 0 1-12.72-6.63c-1.15-1.27-3.39-4.58-3.25-4.82a9 9 0 0 1 1.15-.73L82 101l3.59-2.08l.75 1.11a16.8 16.8 0 0 0 4.74 4.54c4 2.1 9.46 1.81 12.16-.62a5.43 5.43 0 0 0 .69-6.92c-1-1.39-3-2.56-8.59-5c-6.45-2.78-9.23-4.5-11.77-7.24a16.5 16.5 0 0 1-3.43-6.25a25 25 0 0 1-.22-8c1.33-6.23 6-10.58 12.82-11.87a31.7 31.7 0 0 1 9.49.26zm-29.34 5.24v5.12H56.66v46.23H45.15V69.26H28.88v-5a49 49 0 0 1 .12-5.17C29.08 59 39 59 51 59h21.83z"/></svg></span>. 
    
    I have worked on SAAS dashboards, mapping apps and all kinds of user interfaces. In my freetime I enjoy hiking, weightlifting and cooking. -->
    I'm a frontend developer, who specalizes in creating unique and modern user interfaces. I have worked on dashboards, mapping apps, user flows and more.
</p>

<div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<div class="flex flex-col w-full">
    <div class="flex justify-between items-center my-12">
        <div class="text-2xl">
            Projects
        </div>
    </div>
    <div class="flex items-start">
        <div class="h-22 aspect-square bg-[#181828] flex items-center justify-center rounded-md">
            <svg class="h-9 w-9 shrink-0 text-white" viewBox="0 0 24 24"><path fill="currentColor" d="m1 18l6-8l4.5 6H19l-5-6.65l-2.5 3.3L10.25 11L14 6l9 12zm4-2h4l-2-2.675zm0 0h4z"></path></svg>
        </div>
        <div class="flex items-center justify-between grow">
            <div class="flex flex-col ml-4">
                <div class="text-lg font-medium">Coastal UI</div>
                <p class="text-content/80 sm:text-md text-sm mt-1">A library of modern, dark UI elements for Tailwind CSS + Svelte. Over 4,000 unique visitors from Reddit and madewithsvelte.</p>
            </div>
            <div class="h-22 sm:flex items-center hidden">
                <a href="https://www.coastalui.com" target="_blank" class="flex items-center ml-24 mt-2 cursor-pointer group hover:bg-tertiary/10 p-1 rounded-md relative">
                    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 w-30 text-center text-xs opacity-0 group-hover:opacity-100 pointer-events-none transition">
                        Open Website
                    </div>
                    <ExternalLinkIcon strokeWidth={1.5} class="h-5 w-5"/>
                </a>
            </div> 
        </div>
    </div>
    <div class="flex items-start mt-12">
        <div class="h-22 aspect-square bg-[#ff7701] flex items-center justify-center rounded-md">
            <svg class="h-8 w-8 shrink-0" version="1.0" xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 336.000000 306.000000"
                preserveAspectRatio="xMidYMid meet">
                <metadata>
                Created by potrace 1.10, written by Peter Selinger 2001-2011
                </metadata>
                <g transform="translate(0.000000,306.000000) scale(0.100000,-0.100000)"
                fill="#ffffff" stroke="none">
                <path d="M1310 2983 c0 -5 241 -250 536 -546 397 -398 538 -546 544 -570 13
                -48 -1 -101 -27 -105 -12 -2 -27 -10 -33 -18 -11 -12 -170 -14 -1131 -14
                l-1119 0 0 -240 0 -240 1124 0 c783 0 1127 -3 1131 -11 4 -5 18 -14 31 -19 21
                -8 24 -16 24 -61 l0 -52 -184 -191 c-101 -105 -344 -353 -540 -551 -196 -198
                -356 -361 -356 -362 0 -2 140 -3 311 -3 l311 0 700 700 c385 385 706 700 714
                700 11 0 14 18 14 85 0 48 -4 85 -10 85 -5 0 -328 320 -717 710 l-707 710
                -308 0 c-169 0 -308 -3 -308 -7z"/>
                </g>
            </svg>
        </div>
        <div class="flex items-center justify-between grow">
            <div class="flex flex-col ml-4">
                <div class="text-lg font-medium">Clutch Maps</div>
                <p class="text-content/80 mt-1 sm:text-md text-sm">A web app for finding great driving routes near you. Currently built with Svelte + Mapbox, but currently in open beta.</p>
            </div>
            <div class="h-22 sm:flex items-center hidden">
                <a href="https://www.clutchmaps.com" target="_blank" class="flex items-center ml-24 mt-2 cursor-pointer group hover:bg-tertiary/10 p-1 rounded-md relative">
                    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 w-30 text-center text-xs opacity-0 group-hover:opacity-100 pointer-events-none transition">
                        Open Website
                    </div>
                    <ExternalLinkIcon strokeWidth={1.5} class="h-5 w-5"/>
                </a>
            </div> 
        </div>
    </div>
    <div class="flex items-start mt-12">
        <div class="h-22 aspect-square bg-[#00bcff] flex items-center justify-center rounded-md">
            <svg class="h-8 w-8 shrink-0 text-white" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2.1" d="m4 8l4-4m6 0L4 14m0 6L20 4m0 6L10 20m10-4l-4 4"/></svg>
        </div>
        <div class="flex items-center justify-between grow">
            <div class="flex flex-col ml-4">
                <div class="text-lg font-medium">Tailwind BG</div>
                <p class="text-content/80 sm:text-md text-sm mt-1">A colletction of copy-paste tailwind backgrounds. Has the uniqiue ability to test out backgrounds, and even add test content.</p>
            </div>
            <div class="h-22 sm:flex items-center hidden">
                <a href="https://www.tailwindbg.com" target="_blank" class="flex items-center ml-24 mt-2 cursor-pointer group hover:bg-tertiary/10 p-1 rounded-md relative">
                    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 w-30 text-center text-xs opacity-0 group-hover:opacity-100 pointer-events-none transition">
                        Open Website
                    </div>
                    <ExternalLinkIcon strokeWidth={1.5} class="h-5 w-5"/>
                </a>
            </div> 
            
        </div>
    </div>
</div>


<div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<div class="flex flex-col w-full">
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
                    Part of <span class="underline">Clutch Maps</span>
                </div>
                <div class="flex flex-col w-[80vw] sm:w-[430px] relative ">
                    <!-- svelte-ignore a11y_missing_attribute -->
                    <div class="bg-tertiary/10 rounded-md grow flex items-center font-sans z-30">
                        <!-- svelte-ignore a11y_missing_attribute -->
                        <!-- svelte-ignore a11y_consider_explicit_label -->
                        <a
                            class="relative h-[150px] w-[150px] overflow-hidden rounded-l-md bg-content/50 group"
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
                                
                                    <!-- svelte-ignore a11y_missing_attribute -->
                                    <a class="text-[13px] focus:ring-0 h-8 flex items-center justify-center cursor-pointer text-content  py-[2px] rounded-md not-dark:bg-white/70 dark:bg-tertiary/20 border border-secondary/10">
                                        Open in Google Maps    
                                        <svg class="fill-content/80 ml-2 h-4.5 w-4.5" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 48 48"><path fill="currentColor" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" d="M9.5 5.5a4 4 0 0 0-4 4v4.7l28.3 28.3h4.7a4 4 0 0 0 4-4v-29a4 4 0 0 0-4-4zm20.66 3.895a8.446 8.446 0 0 1 8.445 8.447v0c0 4.914-3.995 8.748-8.445 13.774c-4.262-4.812-8.104-8.533-8.423-13.154a8 8 0 0 1-.025-.62a8.446 8.446 0 0 1 8.445-8.448zm0 4.387a4.06 4.06 0 0 0-4.06 4.06v0a4.06 4.06 0 0 0 4.06 4.06h0a4.06 4.06 0 0 0 0-8.12M5.5 27.182V38.5a4 4 0 0 0 4 4h11.32z" stroke-width="1"/></svg>
                                    </a>
                                </div>
                            </div>
                        </div>
                        <!-- svelte-ignore a11y_consider_explicit_label -->
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
            <button out:fade={{duration:100}} onclick={() => currentSlide = currentSlide + 1} class="cursor-pointer absolute right-2 bottom-0 sm:top-1/2 -translate-y-1/2 hover:bg-tertiary/10 rounded-full">
                <ChevronRight class="h-7 w-7 pl-0.5"/>
            </button>
        {/if}
    </div>
</div>

<div class="mt-16 h-[2px] w-full bg-tertiary/20 rounded-full"></div>

<div class="flex flex-col w-full mb-[55vh]">
    <div class="flex justify-between items-center mt-12">
        <div class="text-2xl">
            Let's connect
        </div>
    </div>
    <p class="mb-12 mt-3 text-tertiary">Always interested in joining startups, part-time or full-time development positions.</p>
</div>