<script lang="ts">
	import { links } from "$data/links";
	import { externalLink, HeaderChip, PageSection } from "$lib";
	import { Button, Flyout } from "fluent-svelte";

	import Play from "@fluentui/svg-icons/icons/play_24_regular.svg?raw";
	import List from "@fluentui/svg-icons/icons/list_24_regular.svg?raw";

	let scrollY: number;
</script>

<svelte:window on:scroll={() => window.requestAnimationFrame(() => scrollY = window.scrollY )} />

<PageSection id="design-section">
	<h2>Title</h2>
	<p>
		Description
	</p>
	<div class="buttons-spacer">
		<Button
			href="https://dl.dell.com/topicspdf/xps-13-9300-laptop_reference-guide_en-us.pdf"
			variant="accent"
		>
		{@html Play}
			Play
		</Button>
		<Flyout>
			<Button>
			Price
			</Button>
			<svelte:fragment slot="flyout"> 
				I got mine for £750, though it could be more pricey if it was new.
			</svelte:fragment>
		</Flyout>
	</div>
	<div class="design-image">
		<picture>
			<source
				media="(prefers-color-scheme: dark)"
				srcset="/screenshots/desktop-dark.png"
			>
			<source
				media="(prefers-color-scheme: light)"
				srcset="/screenshots/desktop-light.png"
			>
			<img
				alt="Desktop wallpaper"
				class="files-wallpaper"
				height="900"
				src="/screenshots/desktop-dark.png"
				width="1440"
			>
		</picture>
	</div>
</PageSection>

<style lang="scss">
	@use "WorkstationSection";
</style>
