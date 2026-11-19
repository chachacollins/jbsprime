<script lang="ts">
	import Logo from './Logo.svelte';

	interface NavLink {
		href: string;
		label: string;
	}

	let { links }: { links: NavLink[] } = $props();
</script>

<nav>
	<Logo href="#top" label="JB's Prime Grill &amp; Lounge" />
	<ul>
		{#each links as link}
			<li><a href={link.href}>{link.label}</a></li>
		{/each}
	</ul>
</nav>

<style>
	nav {
		position: relative;
		z-index: 5;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 28px clamp(20px, 5vw, 96px);
	}

	ul {
		display: flex;
		gap: clamp(14px, 2vw, 28px);
		list-style: none;
		margin: 0;
		padding: 0;
	}

	ul a {
		color: var(--red);
		font-weight: 600;
		font-size: 0.85rem;
		letter-spacing: 0.02em;
		text-transform: uppercase;
	}

	ul a:hover {
		color: var(--ink);
	}

	@media (max-width: 760px) {
		ul {
			display: none;
		}
	}
</style>
