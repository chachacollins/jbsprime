<script lang="ts">
	import Hero from '#lib/components/Hero.svelte';
	import About from '#lib/components/About.svelte';
	import MaoriFireBorder from '#lib/components/MaoriFireBorder.svelte';
	import Menu from '#lib/components/Menu.svelte';
	import Gallery from '#lib/components/Gallery.svelte';
	import KidsCorner from '#lib/components/KidsCorner.svelte';
	import Footer from '#lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>JB'S Prime Grill &amp; Lounge</title>
</svelte:head>

<Hero />
<About />
<MaoriFireBorder topColor="#f7f3ee" bottomColor="#f7f3ee" />
<Gallery />
<MaoriFireBorder topColor="#f7f3ee" bottomColor="#f7f3ee" />
<Menu />
<MaoriFireBorder topColor="#f7f3ee" bottomColor="#f7f3ee" />
<KidsCorner />
<MaoriFireBorder topColor="#f7f3ee" bottomColor="#f7f3ee" />
<Footer />
