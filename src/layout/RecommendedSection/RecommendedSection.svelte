<script lang="ts">
	import { externalLink, PageSection, VideoCard } from "$lib";
	import { Button, TextBlock, IconButton } from "fluent-svelte";
	import { links } from "$data/links";
	
	import Play from "@fluentui/svg-icons/icons/play_24_regular.svg?raw";
	import List from "@fluentui/svg-icons/icons/list_24_regular.svg?raw";
	import Creator from "@fluentui/svg-icons/icons/video_person_24_regular.svg?raw";

</script>

<PageSection id="hero-section">
	<div class="hero-left">
	</div>
	<div class="hero-right">
		<VideoCard>
			<svelte:fragment slot="header">
				<TextBlock variant="bodyStrong">Title</TextBlock>
				<IconButton href="https://github.com/"
				>
					{@html Creator}
				</IconButton>
			</svelte:fragment>
		</VideoCard>
	</div>

</PageSection>
<style lang="scss">
	@use "RecommendedSection";
</style>
