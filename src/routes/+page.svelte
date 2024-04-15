<script>
// @ts-nocheck

import { onMount } from "svelte";
import SplitType from "split-type";
import { animate, stagger } from "motion";

// animations
let heroHeading;

onMount(() => {
	
	const splitHeroHeading = new SplitType(heroHeading, {
		types: 'words'
	})
	const paragraph = new SplitType( 'p', {
		types: 'lines'
	})

	const heroElements = [...splitHeroHeading.words, ...paragraph.lines];

	animate(heroElements,
		{y: [24, 0]},
		{opacity: [0, 1]},
		{duration: 0.8, stagger: 0.05}
	)

	//box animation
	animate(
		"#box",
		{ rotate: 90 },
		{
			duration: 5,
			easing: "ease-in-out",
			repeat: 3,
			direction: "alternate"
		}
	)
})

</script>
<!-- hero section -->
<section>
	<div class="h-screen w-full flex items-center justify-center relative">
		<!-- Hero Text -->
		<div class="flex-col">
			<h1 bind:this={heroHeading} class="font-normal text-8xl text-left">
				Benin<br>Mukabanah
			</h1>
			<p class="text-3xl text-left py-8">
				Software Developer Software Developer Software Developer Software Developer Software Developer Software Developer
			</p>

		</div>
	</div>
</section>


<section class="w-full flex items-center justify-center">
	<!-- motion one cube practice -->
	<div id="box" class="w-32 h-32 bg-red-500 rounded-xl">
	</div>
</section>


