<script>
	import Discord from '../Discord.svelte';

	import { CountUp } from 'countup.js';

	function initCount(node, count) {
		const countUp = new CountUp(node, count, { enableScrollSpy: true });
		if (!countUp.error) {
			// countUp.start();
		} else {
			console.error(countUp.error);
		}
	}
	///@ts-ignore
	import Typewriter from 'typewriter-effect/dist/core.js';
	import Github from '../Github.svelte';
	import Chevron from '../Chevron.svelte';
	import GeoBingoLogo from '../GeoBingoLogo.svelte';

	function init(node) {
		new Typewriter(node, {
			strings: ['Sören Michaels', 'Fullstack Developer'],
			loop: true,
			autoStart: true
		});
	}
</script>

<div class="flex flex-col h-screen h-screen ">
	<div class="block md:hidden text-center text-2xl text-white w-full pt-12">
		<div class="" use:init />
	</div>
	<div class="flex justify-around items-center h-full">
		<div class="hidden md:block text-center text-6xl text-white w-full">
			<div class="" use:init />
		</div>
		<div class="bg-white pl-[1px] h-96" />
		<div class="flex justify-center  text-white w-full grid space-y-16">
			<div class="flex items-center justify-center space-x-4">
				<div class="w-12 h-12">
					<Discord />
				</div>
				<span class="md:text-4xl">
					<span class="font-bold">Sören</span><span class="font-thin">#1141</span>
				</span>
			</div>
			<a href="https://github.com/s0er3n" target="_blank">
				<div class="flex items-center justify-center space-x-4">
					<div class="w-12 h-12">
						<Github />
					</div>
					<span class="md:text-4xl">
						<span class="font-thin">github.com/</span><span class="font-bold">s0er3n</span>
					</span>
				</div>
			</a>
			<a href="https://ko-fi.com/soerenmichaels" target="_blank">
				<div class="flex items-center justify-center space-x-4">
					<!-- <div class="w-48 h-12"> -->
					<!-- 	<!-- <img src="kofi.png" /> -->
					<!-- </div> -->
					<span class="md:text-4xl">
						<span class="font-thin">ko-fi.com/</span><span class="font-bold">soerenmichaels</span>
					</span>
				</div>
			</a>
		</div>
	</div>
	<a href="/#geobingo">
		<div class="flex text-white w-full justify-center">
			<div class="flex flex-col">
				<div>Projects</div>
				<Chevron />
			</div>
		</div>
	</a>
</div>

<!-- <div class="p-5" /> -->
<!-- second part  -->
<div id="geobingo" class="h-screen flex font-mono flex-col text-center text-white p-5">
	<div class="flex flex-col h-full justify-around items-center">
		<div class="flex flex-col justify-center w-1/4 h-1/4">
			<GeoBingoLogo />
		</div>
		<div class="p-4">
			<a href="https://geobingo.io" target="_blank"
				><div class="p-5 text-2xl md:text-6xl font-bold  w-full text-center bg-slate-700 ">
					GeoBingo.io
				</div></a
			>
			<div class="grid space-x-4 w-full bg-slate-800 shadow-md rounded-md">
				<p class="text-xl md:text-4xl p-2 font-thin">
					<span class=" font-bold">~<span use:initCount={30} />k</span> monthly players
				</p>
				<p class="text-xl md:text-3xl p-2 font-thin">
					over <span class=" font-bold" use:initCount={400} />K views on YouTube
				</p>
				<p class="text-sm md:text-xl p-2 font-thin">without advertising in under half a year</p>
				<p class="text-xl md:text-2xl p-2 pt-12 font-thin">
					build with <span class="font-bold"> Typescript</span> and
				</p>
				<p class="text-xl md:text-2xl p-4 font-bold">
					SvelteKit NodeJS Tailwindcss Socket.io Docker Google Maps API
				</p>
			</div>
		</div>
	</div>
</div>
