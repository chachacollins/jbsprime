<script lang="ts">
	import Logo from './Logo.svelte';

	interface MenuItem {
		name: string;
		price: string;
	}

	const snackOfTheMonth = {
		title: 'Snack of the Month',
		name: 'THE AMBIORIX',
		description:
			'A BRAND NEW <em>Snack of the Month</em>! AN OLD FAVOURITE THAT MANY HAVE SEEN BUT NEVER TRIED. <em>The Ambiorix</em>! 🔥 IT\'S SUPER SIMPLE. A MEATBALL WITH ONIONS IN BETWEEN! THIS COMBO IS PERFECT! 👌 COME GIVE IT A TRY, BECAUSE WE MAKE THEM OURSELVES! 🤩 SEE YOU SOON! TEAM JB\'S! 🍟',
		price: '3.90 EUR'
	};

	const burgers: MenuItem[] = [
		{ name: 'BICKYBURGER', price: '4.00 EUR' },
		{ name: 'BICKY CHEESE', price: '4.20 EUR' },
		{ name: 'BICKY RIB', price: '4.30 EUR' },
		{ name: 'BICKY CRISPY', price: '4.20 EUR' },
		{ name: 'BICKY CHICKEN', price: '4.50 EUR' },
		{ name: 'BICKY FISH', price: '4.50 EUR' },
		{ name: 'BICKY WRAP', price: '5.00 EUR' },
		{ name: 'CHEESEBURGER', price: '4.00 EUR' },
		{ name: 'HAMBURGER + BUN', price: '3.50 EUR' }
	];

	const fries: MenuItem[] = [
		{ name: 'FRIES KIDS', price: '2.50 EUR' },
		{ name: 'FRIES SMALL', price: '2.70 EUR' },
		{ name: 'FRIES MEDIUM', price: '3.20 EUR' },
		{ name: 'FRIES LARGE', price: '3.70 EUR' },
		{ name: 'FRIES FAMILY SIZE', price: '7.50 EUR' },
		{ name: 'JULIENTJE', price: '9.00 EUR' },
		{ name: 'ROMBOUTJE', price: '9.00 EUR' },
		{ name: 'SNACK BOX', price: '9.00 EUR' }
	];

	const sauces: MenuItem[] = [
		{ name: 'YELLOW BICKY', price: '1.20 EUR' },
		{ name: 'MUSTARD', price: '1.20 EUR' },
		{ name: 'BURGER SAUCE', price: '1.20 EUR' },
		{ name: 'PILI PILI', price: '1.20 EUR' }
	];
</script>

<section class="menu" id="menu">
	<div class="menu-inner">
		<!-- Header -->
		<div class="menu-header">
			<h2 class="menu-title">Menu</h2>
			<div class="menu-logo">
			<Logo href="#top" label="JB's Prime Grill &amp; Lounge" />
		</div>
		</div>

		<!-- Snack van de maand -->
		<div class="snack-card">
			<h3 class="snack-title">{snackOfTheMonth.title}</h3>
			<p class="snack-name">{snackOfTheMonth.name}</p>
			<p class="snack-desc">{@html snackOfTheMonth.description}</p>
			<span class="snack-price">{snackOfTheMonth.price}</span>
		</div>

		<!-- Two-column layout -->
		<div class="columns">
			<!-- Left column: Burgers -->
			<div class="col-left">
				<div class="category">
					<div class="category-header">
						<svg class="category-icon" viewBox="0 0 60 50" aria-hidden="true">
							<path d="M10 24 Q12 6 30 6 Q48 6 50 24Z" fill="none" stroke="var(--red)" stroke-width="2"/>
							<path d="M8 30 Q16 38 24 30 Q32 38 40 30 Q48 38 54 30" fill="none" stroke="var(--red)" stroke-width="2"/>
							<path d="M10 36 H50" stroke="var(--red)" stroke-width="2"/>
							<path d="M12 36 Q14 48 30 48 Q46 48 48 36" fill="none" stroke="var(--red)" stroke-width="2"/>
						</svg>
						<h3 class="category-title">Burgers</h3>
					</div>
					{#each burgers as item}
						<div class="menu-item">
							<span class="item-name">{item.name}</span>
							<span class="item-dots"></span>
							<span class="item-price">{item.price}</span>
						</div>
					{/each}
				</div>
			</div>

			<!-- Right column: Frietjes + Sauzen -->
			<div class="col-right">
				<div class="category">
					<div class="category-header">
						<svg class="category-icon" viewBox="0 0 60 60" aria-hidden="true">
							<path d="M18 30 L24 58 H36 L42 30Z" fill="none" stroke="var(--red)" stroke-width="2"/>
							<path d="M22 28 L20 8 M28 28 L27 4 M34 28 L36 6 M40 28 L44 10" stroke="var(--red)" stroke-width="2.5" stroke-linecap="round"/>
						</svg>
						<h3 class="category-title">Fries</h3>
					</div>
					{#each fries as item}
						<div class="menu-item">
							<span class="item-name">{item.name}</span>
							<span class="item-dots"></span>
							<span class="item-price">{item.price}</span>
						</div>
					{/each}
				</div>

				<div class="category">
					<div class="category-header">
						<svg class="category-icon" viewBox="0 0 60 50" aria-hidden="true">
							<rect x="8" y="12" width="44" height="8" rx="4" fill="none" stroke="var(--red)" stroke-width="2"/>
							<path d="M14 20 L14 36 Q14 44 30 44 Q46 44 46 36 L46 20" fill="none" stroke="var(--red)" stroke-width="2"/>
							<path d="M22 28 L38 28" stroke="var(--red)" stroke-width="1.5"/>
						</svg>
						<h3 class="category-title">Sauces</h3>
					</div>
					{#each sauces as item}
						<div class="menu-item">
							<span class="item-name">{item.name}</span>
							<span class="item-dots"></span>
							<span class="item-price">{item.price}</span>
						</div>
					{/each}
				</div>
			</div>
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

	/* Header */
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

	/* Snack van de maand */
	.snack-card {
		background: var(--red, #ff3b47);
		color: #f7f3ee;
		border-radius: 24px;
		padding: clamp(24px, 3vw, 40px) clamp(24px, 3vw, 48px);
		margin-bottom: clamp(32px, 4vw, 56px);
		max-width: 680px;
	}

	.snack-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(1.6rem, 3.5vw, 2.6rem);
		margin: 0 0 16px;
		line-height: 1.1;
	}

	.snack-name {
		font-weight: 700;
		font-size: 0.9rem;
		letter-spacing: 0.04em;
		margin: 0 0 8px;
	}

	.snack-desc {
		font-weight: 600;
		font-size: 0.82rem;
		line-height: 1.5;
		margin: 0 0 16px;
		text-transform: uppercase;
	}

	.snack-desc :global(em) {
		font-style: italic;
		font-weight: 700;
	}

	.snack-price {
		display: inline-block;
		background: rgba(0, 0, 0, 0.18);
		color: #f7f3ee;
		font-weight: 700;
		font-size: 0.78rem;
		padding: 6px 16px;
		border-radius: 99px;
		letter-spacing: 0.04em;
	}

	/* Columns */
	.columns {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: clamp(32px, 5vw, 80px);
	}

	/* Category */
	.category {
		margin-bottom: clamp(32px, 4vw, 56px);
	}

	.category-header {
		margin-bottom: clamp(16px, 2vw, 28px);
	}

	.category-icon {
		width: 40px;
		height: auto;
		display: block;
		margin-bottom: 4px;
	}

	.category-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(2rem, 4vw, 3.2rem);
		margin: 0;
		line-height: 1.1;
		color: #66242b;
	}

	/* Menu items */
	.menu-item {
		display: flex;
		align-items: baseline;
		padding: 10px 0;
		gap: 8px;
	}

	.item-name {
		font-weight: 700;
		font-size: 0.82rem;
		letter-spacing: 0.04em;
		white-space: nowrap;
		flex-shrink: 0;
	}

	.item-dots {
		flex: 1;
		border-bottom: 2px dotted rgba(102, 36, 43, 0.3);
		min-width: 20px;
		margin-bottom: 3px;
	}

	.item-price {
		flex-shrink: 0;
		font-weight: 600;
		font-size: 0.78rem;
		letter-spacing: 0.03em;
		padding: 4px 14px;
		border: 1.5px solid #66242b;
		border-radius: 99px;
		white-space: nowrap;
	}

	/* Responsive */
	@media (max-width: 860px) {
		.columns {
			grid-template-columns: 1fr;
		}

		.snack-card {
			max-width: 100%;
		}
	}
</style>
