<script lang="ts">
	let { href, label }: { href: string; label: string } = $props();
</script>

<a class="logo" {href} aria-label={label}>
	JB's<small>PRIME GRILL</small>
</a>

<style>
	.logo {
		font-family: var(--serif);
		font-style: italic;
		font-size: 1.9rem;
		line-height: 1;
		color: var(--ink);
	}

	.logo small {
		display: block;
		font-family: var(--sans);
		font-style: normal;
		font-size: 0.6rem;
		letter-spacing: 0.2em;
		margin-top: 6px;
	}
</style>
