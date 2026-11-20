<script lang="ts">
	import Logo from './Logo.svelte';
</script>

<section class="menu" id="menu">
	<div class="menu-inner">
		<div class="menu-header">
			<h2 class="menu-title">Menu</h2>
			<div class="menu-logo">
				<Logo href="#top" label="JB's Prime Grill &amp; Lounge" />
			</div>
		</div>

		<div class="coming-soon">
			<div class="coming-soon-icon">
				<svg viewBox="0 0 80 80" aria-hidden="true">
					<circle cx="40" cy="40" r="34" fill="none" stroke="var(--red)" stroke-width="2.5" stroke-dasharray="6 4" />
					<path d="M40 20 V42 L54 50" fill="none" stroke="var(--red)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" />
				</svg>
			</div>
			<h3 class="coming-soon-title">Coming Soon</h3>
			<p class="coming-soon-text">
				We're still perfecting every recipe. Our full menu will be revealed when the doors open — stay tuned!
			</p>
		</div>
	</div>
</section>

<style>
	.menu {
		background: #f7f3ee;
		color: #66242b;
		padding: clamp(40px, 6vw, 80px) clamp(20px, 5vw, 96px);
	}

	.menu-inner {
		max-width: 1400px;
		margin: 0 auto;
	}

	.menu-header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: clamp(24px, 3vw, 40px);
	}

	.menu-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(3rem, 7vw, 6rem);
		line-height: 1;
		margin: 0;
		color: #66242b;
	}

	.menu-logo {
		flex-shrink: 0;
		color: #66242b;
	}

	.coming-soon {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		padding: clamp(48px, 6vw, 100px) 20px;
	}

	.coming-soon-icon {
		width: 80px;
		height: 80px;
		margin-bottom: 24px;
		animation: pulse 2.5s ease-in-out infinite;
	}

	@keyframes pulse {
		0%, 100% { opacity: 1; transform: scale(1); }
		50% { opacity: 0.6; transform: scale(1.08); }
	}

	.coming-soon-icon svg {
		width: 100%;
		height: 100%;
	}

	.coming-soon-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(2rem, 4vw, 3.4rem);
		margin: 0 0 16px;
		color: var(--red);
		line-height: 1.1;
	}

	.coming-soon-text {
		max-width: 42ch;
		font-weight: 600;
		font-size: 0.95rem;
		line-height: 1.5;
		margin: 0;
		color: #66242b;
		opacity: 0.75;
	}

	@media (prefers-reduced-motion: reduce) {
		.coming-soon-icon {
			animation: none;
		}
	}
</style>
