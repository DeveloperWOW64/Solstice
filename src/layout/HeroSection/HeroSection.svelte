<script lang="ts">
	import { externalLink, PageSection } from "$lib";
	import { Button } from "fluent-svelte";
	import { links } from "$data/links";
	import Play from "@fluentui/svg-icons/icons/play_24_regular.svg?raw";
	import List from "@fluentui/svg-icons/icons/list_24_regular.svg?raw";

</script>

<PageSection id="hero-section">
	<div class="hero-left">
		<p>I'm a developer from the UK.</p>
		<div class="buttons-spacer">
			<Button
				variant="accent"
				href="https://github.com/{links.github.owner}/?tab=repositories"
				{...externalLink}
			>
				{@html Play}
				<div class="hero-button-inner">
					<h5>Play</h5>
				</div>
			</Button>
			<Button
				href="https://github.com/files-community"
				{...externalLink}
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
					srcset="/screenshots/hero-dark.png"
				>
				<source
					media="(prefers-color-scheme: light)"
					srcset="/screenshots/hero-light.png"
				>
				<img
					alt="Files new tab screenshot"
					height="768"
					src="/screenshots/hero-light.png"
					width="1024"
				>
			</picture>
		</div>
	</div>
	<div class="rainbow-background" slot="outer"></div>
</PageSection>
<style lang="scss">
	@use "HeroSection";
</style>
