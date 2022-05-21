<script lang="ts">
	import { externalLink, PageSection } from "$lib";
	import { Button } from "fluent-svelte";
	import { links } from "$data/links";
	
	import Play from "@fluentui/svg-icons/icons/play_24_regular.svg?raw";
	import List from "@fluentui/svg-icons/icons/list_24_regular.svg?raw";

</script>

<PageSection id="hero-section">
	<div class="hero-left">
		<h2>HeroRecommendedVideo.Title</h2>
		<p>HeroRecommendedVideo.Description</p>
		<div class="buttons-spacer">
			<Button
				variant="accent"
				href="/player/"
			>
				{@html Play}
				<div class="hero-button-inner">
					<h5>Play</h5>
				</div>
			</Button>
			<Button
				href="/lib/add.svelte?video="
			>
				{@html List}
				<div class="hero-button-inner">
					<h5>Watch Later</h5>
				</div>
			</Button>
		</div>
	</div>
	<div class="hero-right">
		<div class="hero-image-container">
			<picture>
				<source
					media="(prefers-color-scheme: dark)"
				>
				<source
					media="(prefers-color-scheme: light)"
				>
				<img
					alt="HeroRecommendedVideo"
				>
			</picture>
		</div>
	</div>
	<div class="rainbow-background" slot="outer"></div>
</PageSection>
<style lang="scss">
	@use "HeroSection";
</style>
