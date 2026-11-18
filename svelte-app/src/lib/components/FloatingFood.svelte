<script lang="ts">
	import type { Snippet } from 'svelte';

	interface FloatingFoodProps {
		x: string;
		y: string;
		w: string;
		d: string;
		dx: string;
		dy: string;
		r: string;
		sd: string;
		delay?: string;
		color: 'gold' | 'red' | 'white';
		top?: boolean;
		hideOnMobile?: boolean;
		children: Snippet;
	}

	let {
		x,
		y,
		w,
		d,
		dx,
		dy,
		r,
		sd,
		delay = '0s',
		color,
		top = false,
		hideOnMobile = false,
		children
	}: FloatingFoodProps = $props();
</script>

<div
	class="f {color}"
	class:top
	class:hide-m={hideOnMobile}
	style="--x:{x};--y:{y};--w:{w};--d:{d};--dx:{dx};--dy:{dy};--r:{r};--sd:{sd};--delay:{delay}"
>
	{@render children()}
</div>

<style>
	.f {
		position: absolute;
		z-index: 2;
		width: var(--w);
		left: var(--x);
		top: var(--y);
		pointer-events: none;
		animation: float var(--d) ease-in-out var(--delay, 0s) infinite alternate;
		will-change: transform;
	}

	.f :global(svg) {
		display: block;
		width: 100%;
		height: auto;
		overflow: visible;
		animation: spin var(--sd) ease-in-out var(--delay, 0s) infinite alternate;
	}

	.f.top {
		z-index: 4;
	}

	.f :global(path),
	.f :global(ellipse),
	.f :global(circle),
	.f :global(rect),
	.f :global(line) {
		fill: none;
		stroke-width: 5;
		stroke-linecap: round;
		stroke-linejoin: round;
	}

	.gold :global(*) {
		stroke: var(--gold);
	}
	.red :global(*) {
		stroke: var(--red);
	}
	.white :global(*) {
		stroke: var(--ink);
	}

	@keyframes float {
		0% {
			transform: translate3d(0, 0, 0);
		}
		50% {
			transform: translate3d(var(--dx), calc(var(--dy) * -0.4), 0);
		}
		100% {
			transform: translate3d(calc(var(--dx) * -1), var(--dy), 0);
		}
	}

	@keyframes spin {
		from {
			transform: rotate(calc(var(--r) * -1));
		}
		to {
			transform: rotate(var(--r));
		}
	}

	@media (max-width: 760px) {
		.hide-m {
			display: none;
		}
	}
</style>
