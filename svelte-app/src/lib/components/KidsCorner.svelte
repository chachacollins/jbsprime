<script lang="ts">
	interface Feature {
		icon: string;
		title: string;
		description: string;
	}

	const features: Feature[] = [
		{
			icon: `<circle cx="20" cy="20" r="18" fill="none" stroke="currentColor" stroke-width="1.8"/>
				   <circle cx="14" cy="16" r="1.5" fill="currentColor"/>
				   <circle cx="26" cy="16" r="1.5" fill="currentColor"/>
				   <path d="M13,24 Q20,30 27,24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>`,
			title: 'A Menu for Small Appetites',
			description:
				'Mini burgers, grilled chicken strips, chips and fruit — proper food, sized for children and priced for families.'
		},
		{
			icon: `<rect x="6" y="8" width="28" height="20" rx="2" fill="none" stroke="currentColor" stroke-width="1.8"/>
				   <path d="M14,28 L14,34 M26,28 L26,34 M10,34 L30,34" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>`,
			title: 'Play Area',
			description:
				'A supervised corner for playing games, so the grown-ups can finish their meal while the children are happily occupied.'
		},
		{
			icon: `<path d="M12,30 L12,16 Q12,8 20,8 L24,8 Q28,8 28,12 L28,14" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
				   <path d="M8,30 L32,30" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
				   <path d="M18,8 L18,4 M22,8 L22,2 M26,8 L26,5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
				   <rect x="8" y="30" width="24" height="4" rx="1" fill="none" stroke="currentColor" stroke-width="1.8"/>`,
			title: 'Birthdays & Treats',
			description:
				'Book a table for a birthday and we will set it up with a cake, candles and a small gift for the birthday child.'
		}
	];
</script>

<section class="kids" id="kids">
	<div class="kids-inner">
		<h2>Kids Corner</h2>
		<p class="intro">
			Families are welcome at JB'S Prime. The little ones get their own menu, their own space and
			a table where nobody has to sit still.
		</p>

		<div class="features">
			{#each features as feature}
				<div class="feature">
					<div class="icon-wrap">
						<svg viewBox="0 0 40 40" aria-hidden="true">
							{@html feature.icon}
						</svg>
					</div>
					<div class="feature-text">
						<h3>{feature.title}</h3>
						<p>{feature.description}</p>
					</div>
				</div>
			{/each}
		</div>

		<p class="closing">
			High chairs and a warm welcome for every family — no booking needed for the kids corner.
		</p>
	</div>
</section>

<style>
	.kids {
		background: #f7f3ee;
		color: var(--bg, #66242b);
		padding: clamp(56px, 8vw, 100px) clamp(20px, 5vw, 96px);
	}

	.kids-inner {
		max-width: 1100px;
		margin: 0 auto;
		text-align: center;
	}

	h2 {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(2.6rem, 5.5vw, 4.4rem);
		line-height: 1;
		margin: 0 0 clamp(16px, 2vw, 28px);
		color: var(--bg, #66242b);
	}

	.intro {
		max-width: 48ch;
		margin: 0 auto clamp(36px, 5vw, 64px);
		font-size: clamp(0.9rem, 1.1vw, 1rem);
		line-height: 1.55;
		font-weight: 400;
	}

	/* Features — horizontal rows, not floating cards */
	.features {
		display: flex;
		flex-direction: column;
		gap: 0;
		margin-bottom: clamp(36px, 5vw, 64px);
		text-align: left;
	}

	.feature {
		display: flex;
		align-items: flex-start;
		gap: clamp(16px, 2vw, 28px);
		padding: clamp(20px, 2.5vw, 32px) 0;
		border-top: 1.5px dotted rgba(102, 36, 43, 0.25);
	}

	.feature:last-child {
		border-bottom: 1.5px dotted rgba(102, 36, 43, 0.25);
	}

	/* Icon */
	.icon-wrap {
		width: 48px;
		height: 48px;
		flex-shrink: 0;
		border-radius: 50%;
		border: 1.5px solid var(--bg, #66242b);
		display: flex;
		align-items: center;
		justify-content: center;
		color: var(--red, #ff3b47);
		margin-top: 2px;
	}

	.icon-wrap svg {
		width: 24px;
		height: 24px;
	}

	.feature-text {
		flex: 1;
	}

	.feature h3 {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(1.2rem, 1.8vw, 1.6rem);
		margin: 0 0 6px;
		color: var(--bg, #66242b);
	}

	.feature p {
		margin: 0;
		font-weight: 600;
		font-size: 0.85rem;
		line-height: 1.5;
		letter-spacing: 0.02em;
		text-transform: uppercase;
		color: rgba(102, 36, 43, 0.65);
		max-width: 50ch;
	}

	/* Closing italic note */
	.closing {
		font-family: var(--serif);
		font-style: italic;
		font-size: clamp(0.95rem, 1.2vw, 1.1rem);
		line-height: 1.45;
		color: var(--red, #ff3b47);
		max-width: 42ch;
		margin: 0 auto;
	}

	@media (max-width: 600px) {
		.feature {
			flex-direction: column;
			gap: 12px;
		}
	}
</style>
