<script lang="ts">
	import '../app.css';
	import { ModeWatcher, toggleMode } from "mode-watcher";
	import { Moon } from 'lucide-svelte';
	// @ts-ignore
    import ScrollTracker from 'svelte-scroll-tracker';
	let { children } = $props();
</script>

<ModeWatcher />
<div class="min-h-screen bg-background flex justify-center relative overflow-hidden">
	<div class="mx-auto max-w-[750px] flex flex-col w-full h-full relative pt-16 px-3 xl:px-0">
		<div class="-top-6 hidden sm:flex -left-[500px] not-dark:hidden w-[900px] h-24 bg-zinc-500/10 rounded-full rotate-10 blur-[40px] absolute">
		</div>
		{@render children()}
	</div>
    <ScrollTracker>
		<div class="absolute left-1/2 -translate-x-1/2 top-0 w-32 bg-white h-12 hidden">
			{#snippet children(progress:any)}
				{#if progress > .1}
					<div class="flex">

					</div>
				{/if}
			{/snippet}
		</div>
    </ScrollTracker>
</div>
