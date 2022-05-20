<script context="module" lang="ts">
</script>

<script lang="ts">
	import { PageSection, Metadata } from "$lib";
	import { ContentDialog, Button } from "fluent-svelte";


	let scrollY: number;
</script>

<svelte:head>
	<Metadata title="Login" image="acc" />
</svelte:head>

<svelte:window on:scroll={() => window.requestAnimationFrame(() => scrollY = window.scrollY )} />

<PageSection>
	<div class="blog-backdrop">
		<img
			alt="Banner"
			src="/branding/banner.png"
			style:transform="translateY({Math.floor(scrollY / 2.5)}px)"
			width="0"
		>
	</div>
	<div class="main-post">
		<div class="about">
			<ContentDialog open title="Succesfully logged in.">
				You may now return home.
				<br/>
				<svelte:fragment slot="footer">
				<Button href="/">
					Return Home
				</Button>
			</svelte:fragment>
			</ContentDialog>
		</div>
	</div>	
</PageSection>

<style lang="scss">
	@use "../src/styles/pages/trends.scss";
</style>