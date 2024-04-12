<script>
// @ts-nocheck

import { onMount } from "svelte";
import SplitType from "split-type";
import { animate, stagger } from "motion";

// animations
let heroHeading;
let heroSubHeading;

onMount(() => {
	
	const splitHeroHeading = new SplitType(heroHeading, {
		types: 'words'
	})
	const splitHeroSubHeading = new SplitType( heroSubHeading, {
		types: 'lines'
	})

	const heroElements = [...splitHeroHeading.words, ...splitHeroSubHeading.lines];

	animate(heroElements,
		{y: [69, 0]},
		{opacity: [0, 1]},
		{delay: stagger(0.05), duration: 2}
	)
})

</script>
<!-- hero section -->
<section>
	<div class="h-screen w-full flex items-center justify-center relative">
		<!-- Hero Text -->
		<div class="flex-col">
			<h1  bind:this={heroHeading} class="font-normal text-8xl text-left">
				Benin<br>Mukabanah
			</h1>
			<h3 bind:this={heroSubHeading} class="text-3xl text-left py-8">
				Software Developer
			</h3>
		</div>
	</div>
</section>


