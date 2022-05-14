<script lang="ts">
	import { page } from "$app/stores";

	export let title = "Solstice";
	export let image = "/branding/logo.png";
	$: imageFile = image.startsWith("/") ? image : `/branding/banner-${image}.png`
</script>

<title>{title}</title>
<meta content={title} name="og:title">
<meta content={title} name="twitter:title">

<meta content={imageFile} name="og:image">
<meta content="https://{$page.url.host}{imageFile}" name="twitter:image">