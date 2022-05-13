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

<div class="flex flex-col h-screen">
	<div class="flex justify-around items-center h-full">
		<div class=" text-center text-6xl text-white w-full">
			<div class="" use:init />
		</div>
		<div class="bg-white pl-[1px] h-96" />
		<div class="flex justify-center  text-white w-full grid space-y-16">
			<div class="flex items-center justify-center space-x-4">
				<div class="w-12 h-12">
					<Discord />
				</div>
				<span class="text-4xl">
					<span class="font-bold">Sören</span><span class="font-thin">#1141</span>
				</span>
			</div>
			<a href="https://github.com/s0er3n" target="_blank">
				<div class="flex items-center justify-center space-x-4">
					<div class="w-12 h-12">
						<Github />
					</div>
					<span class="text-4xl">
						<span class="font-thin">github.com/</span><span class="font-bold">s0er3n</span>
					</span>
				</div>
			</a>
			<a href="https://ko-fi.com/soerenmichaels" target="_blank">
				<div class="flex items-center justify-center space-x-4">
					<!-- <div class="w-48 h-12"> -->
					<!-- 	<!-- <img src="kofi.png" /> -->
					<!-- </div> -->
					<span class="text-4xl">
						<span class="font-thin">ko-fi.com/</span><span class="font-bold">soerenmichaels</span>
					</span>
				</div>
			</a>
		</div>
	</div>
	<a href="/#geobingo">
		<div class="flex h-8 text-white w-full justify-center">
			<Chevron />
		</div>
	</a>
</div>
<!-- second part  -->
<div id="geobingo" class=" h-screen flex font-mono flex-col text-center text-white">
	<div class="p-5 text-6xl font-bold  w-full text-center ">GeoBingo.io</div>
	<div class="flex h-full justify-around items-center">
		<div class="flex flex-col justify-center w-full h-full">
			<GeoBingoLogo />
		</div>
		<div class="grid space-x-4 w-full">
			<p class="text-6xl p-4 font-thin">
				<span class=" font-bold">~<span use:initCount={30} />k</span> monthly players
			</p>
			<p class="text-3xl p-4 font-thin">
				over <span class=" font-bold" use:initCount={400} />K views on YouTube
			</p>
			<p class="text-xl p-2 font-thin">without advertising in under half a year</p>
			<p class="text-2xl p-4 pt-24 font-thin">
				build with <span class="font-bold"> Typescript</span> and
			</p>
			<p class="text-2xl p-4 font-bold">
				SvelteKit NodeJS Tailwindcss Socket.io Docker Google Maps API
			</p>
		</div>
	</div>
</div>
