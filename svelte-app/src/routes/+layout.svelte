<script lang="ts">
	import type { Snippet } from 'svelte';

	let { children }: { children: Snippet } = $props();
</script>

{@render children()}

<style>
	:global(:root) {
		--bg: #66242b;
		--ink: #f7f3ee;
		--red: #ff3b47;
		--gold: #f0d23c;
		--serif: 'Instrument Serif', 'Times New Roman', Georgia, serif;
		--sans: 'Archivo', system-ui, -apple-system, 'Segoe UI', Arial, sans-serif;
		box-sizing: border-box;
		padding-top: env(safe-area-inset-top, 0px);
		padding-bottom: env(safe-area-inset-bottom, 0px);
	}

	:global(html) {
		scroll-padding-top: env(safe-area-inset-top, 0px);
	}

	:global(*),
	:global(*::before),
	:global(*::after) {
		box-sizing: inherit;
	}

	:global(html),
	:global(body) {
		margin: 0;
	}

	:global(body) {
		background: var(--bg);
		color: var(--ink);
		font-family: var(--sans);
		overflow-x: hidden;
	}

	:global(a) {
		color: inherit;
		text-decoration: none;
	}

	:global(a:focus-visible) {
		outline: 2px solid var(--gold);
		outline-offset: 4px;
	}

	@media (prefers-reduced-motion: reduce) {
		:global(.f),
		:global(.f svg) {
			animation: none;
		}
		:global(.card) {
			transition: none;
		}
		:global(html.js .card:not(.in)) {
			opacity: 1;
			transform: rotate(var(--r));
		}
	}
</style>
