<script lang="ts">
	import { dev } from "$app/env";
	import { page } from "$app/stores";
	import { onMount } from "svelte";

	import { Footer, Navbar } from "$layout";
	import { links, NavbarItem } from "$data/links";
	import { docs } from "$data/docs";

	import "fluent-svelte/theme.css";

	import Code from "@fluentui/svg-icons/icons/code_24_regular.svg?raw";
	import Home from "@fluentui/svg-icons/icons/home_24_regular.svg?raw";
	import Trending from "@fluentui/svg-icons/icons/arrow_trending_24_regular.svg?raw";
	import Library from "@fluentui/svg-icons/icons/library_24_regular.svg?raw";
	import Person from "@fluentui/svg-icons/icons/person_24_regular.svg?raw";
	import Settings from "@fluentui/svg-icons/icons/settings_24_regular.svg?raw";

	const { github, discord } = links;

	const navbarItems: NavbarItem[] = [
		{
			name: "Home",
			path: "/",
			icon: Home
		},
		{
			name: "Trending",
			path: "/trends",
			icon: Trending
		},
		{
			name: "Library",
			path: "/acc/lib",
			sidebarTree: docs,
			icon: Library
		},
	];

	let navbarButtons = [
		{
			label: "Settings",
			href: "/prefs",
			icon: Settings
		}
	];

	if (dev) {
		navbarButtons.push(
		{
			label: "Code",
			href: "https://github.com/DeveloperWOW64/Solstice",
			icon: Code
		}
		);
		navbarButtons = navbarButtons;
	}

	let theme: "light" | "dark" = "light";

	onMount(() => {
		theme = window?.matchMedia("(prefers-color-scheme: dark)")?.matches ? "dark" : "light";

		window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", e => {
			theme = e.matches ? "dark" : "light";
		});
	});

</script>

<svelte:head>
	<meta content="Solstice" name="og:site_name">

	<meta content="website" name="og:type">

	<link
		href="/branding/logo.png"
		rel="icon"
		type="image/svg+xml"
	>
	<meta
		content="Solstice, Tikka, Jupiter, DeveloperWOW64, Developer, Fluent, Svelte, Eclipse, computer, code, Codrex, Andrex, Python, XAML, Fluent-Svelte, Files, DeveloperWEB64, DeveloperDWNLD64, DownloadWEB64, "
		name="keywords"
	>

	<meta content="#084840" name="theme-color">

	<meta content="summary_large_image" name="twitter:card">
	<meta content="@DeveloperWOW64" name="twitter:site">
	<meta content="@DeveloperWOW64" name="twitter:creator">
</svelte:head>

<Navbar buttons={navbarButtons} items={navbarItems} />
<slot />
<Footer />

<style global lang="scss">
	@use "src/styles/global";
	@use "src/styles/markdown";
</style>
