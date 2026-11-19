<script lang="ts">
	interface CardData {
		style: string;
		label: string;
		caption: string;
		svg: string;
	}

	const cards: CardData[] = [
		{
			style: '--l:0%;--t:14%;--r:-8deg;--dl:0s',
			label: 'Illustration of a stacked burger',
			caption: 'Signature burger',
			svg: '<rect width="200" height="300" fill="#c8283a"/><circle cx="100" cy="170" r="92" fill="#d8404f"/><rect x="140" y="50" width="12" height="70" rx="3" fill="#f0d23c" transform="rotate(25 146 85)"/><rect x="158" y="60" width="12" height="60" rx="3" fill="#f0d23c" transform="rotate(40 164 90)"/><rect x="40" y="46" width="12" height="64" rx="3" fill="#f0d23c" transform="rotate(-30 46 78)"/><path d="M40 150Q40 90 100 90Q160 90 160 150Z" fill="#e8a43a"/><ellipse cx="78" cy="114" rx="5" ry="2.5" fill="#fff3d0"/><ellipse cx="104" cy="106" rx="5" ry="2.5" fill="#fff3d0"/><ellipse cx="124" cy="124" rx="5" ry="2.5" fill="#fff3d0"/><ellipse cx="96" cy="132" rx="5" ry="2.5" fill="#fff3d0"/><path d="M34 150Q46 166 60 150Q74 166 88 150Q102 166 116 150Q130 166 144 150Q156 166 166 150V158H34Z" fill="#6bb04a"/><path d="M38 160H162L150 182 130 168 110 186 90 168 70 186 50 168Z" fill="#f0b429"/><rect x="40" y="176" width="120" height="26" rx="13" fill="#5a2a1a"/><path d="M42 206H158Q158 238 100 238Q42 238 42 206Z" fill="#e8a43a"/>'
		},
		{
			style: '--l:33%;--t:0%;--r:5deg;--dl:.15s',
			label: 'Illustration of a steak over open flame',
			caption: 'Prime cut steak',
			svg: '<rect width="200" height="300" fill="#2b1417"/><path d="M0 300V250Q20 210 36 250Q52 200 70 250Q90 190 106 250Q126 205 144 250Q160 215 176 250Q190 230 200 250V300Z" fill="#ff7a1a"/><path d="M0 300V272Q24 240 44 272Q66 232 88 272Q110 236 132 272Q154 240 176 272Q190 258 200 272V300Z" fill="#f0d23c"/><g stroke="#6b5a5a" stroke-width="4"><path d="M0 196H200M0 216H200M0 236H200"/></g><path d="M30 130Q24 70 80 66Q142 58 170 104Q188 146 144 180Q86 204 50 176Q32 160 30 130Z" fill="#8a3a22"/><g stroke="#3a1810" stroke-width="6" stroke-linecap="round"><path d="M62 92L120 150M84 80L146 142M48 118L100 168"/></g><circle cx="132" cy="100" r="13" fill="#f7f3ee"/><circle cx="132" cy="100" r="6" fill="#e5d5c0"/><path d="M150 70Q168 50 156 30M60 56Q50 36 64 20" fill="none" stroke="#f7f3ee" stroke-width="4" stroke-linecap="round" opacity=".6"/><path d="M28 188Q50 170 74 176" fill="none" stroke="#6bb04a" stroke-width="4" stroke-linecap="round"/>'
		},
		{
			style: '--l:66%;--t:24%;--r:-4deg;--dl:.3s',
			label: 'Illustration of a cocktail glass',
			caption: 'Lounge cocktails',
			svg: '<rect width="200" height="300" fill="#1f8a70"/><circle cx="100" cy="140" r="86" fill="#27a082"/><path d="M40 80H160L100 160Z" fill="#f7f3ee" opacity=".92"/><path d="M52 100H148L100 160Z" fill="#ff3b47"/><path d="M100 160V228M66 238H134" stroke="#f7f3ee" stroke-width="7" stroke-linecap="round"/><path d="M128 96L152 40" stroke="#f0d23c" stroke-width="5" stroke-linecap="round"/><circle cx="156" cy="82" r="16" fill="#f0a030"/><circle cx="156" cy="82" r="11" fill="#ffd27a"/><path d="M156 71V93M145 82H167" stroke="#f0a030" stroke-width="2"/><circle cx="84" cy="122" r="4" fill="#f7f3ee" opacity=".7"/><circle cx="104" cy="114" r="3" fill="#f7f3ee" opacity=".7"/><circle cx="116" cy="130" r="3" fill="#f7f3ee" opacity=".7"/>'
		}
	];

	let cardElements: HTMLElement[] = $state([]);

	function observeCards() {
		if (typeof IntersectionObserver === 'undefined') {
			cardElements.forEach((c) => c?.classList.add('in'));
			return;
		}

		const io = new IntersectionObserver(
			(entries) => {
				entries.forEach((e) => {
					if (e.isIntersecting) {
						e.target.classList.add('in');
						io.unobserve(e.target);
					}
				});
			},
			{ threshold: 0.25 }
		);

		cardElements.forEach((c) => {
			if (c) io.observe(c);
		});
	}

	$effect(() => {
		document.documentElement.classList.add('js');
		observeCards();
	});
</script>

<section class="about" id="about">
	<div class="about-in">
		<div class="cards">
			{#each cards as card, i}
				<figure class="card" style={card.style} bind:this={cardElements[i]}>
					<svg
						viewBox="0 0 200 300"
						preserveAspectRatio="xMidYMid slice"
						role="img"
						aria-label={card.label}
					>
						{@html card.svg}
					</svg>
					<figcaption>{card.caption}</figcaption>
				</figure>
			{/each}
		</div>

		<div class="copy">
			<h2>Hey, welcome to JB's</h2>
			<p>
				JB's Prime Grill &amp; Lounge is where the fire never goes out. Every cut is seasoned
				in-house, grilled over open flame and served with fries cooked fresh to order.
			</p>
			<blockquote>
				"For us, two things matter: the meat is always prime, and the evening is never rushed."
			</blockquote>
			<p class="close">Come by, pull up a seat and taste why our guests keep coming back.</p>
		</div>
	</div>
</section>

<style>
	.about {
		background: #f7f3ee;
		color: var(--bg);
		padding: clamp(56px, 9vw, 120px) clamp(20px, 5vw, 96px);
		overflow: hidden;
	}

	.about-in {
		max-width: 1500px;
		margin: 0 auto;
		display: grid;
		grid-template-columns: 1.1fr 1fr;
		gap: clamp(32px, 5vw, 80px);
		align-items: center;
	}

	.cards {
		position: relative;
		aspect-ratio: 1 / 0.85;
	}

	.card {
		position: absolute;
		margin: 0;
		width: 34%;
		aspect-ratio: 2 / 3;
		border-radius: 28px;
		overflow: hidden;
		box-shadow: 0 18px 40px rgba(60, 10, 15, 0.22);
		left: var(--l);
		top: var(--t);
		transform: rotate(var(--r));
		transition:
			transform 1.1s cubic-bezier(0.2, 0.8, 0.2, 1) var(--dl),
			opacity 0.8s ease var(--dl);
	}

	.card :global(svg) {
		display: block;
		width: 100%;
		height: 100%;
	}

	.card figcaption {
		position: absolute;
		left: 12px;
		bottom: 12px;
		background: var(--ink);
		color: var(--bg);
		font-weight: 700;
		font-size: 0.72rem;
		padding: 6px 12px;
		border-radius: 99px;
	}

	:global(html.js) .card:not(:global(.in)) {
		opacity: 0;
		transform: translateY(70px) rotate(0deg);
	}

	.about :global(h2) {
		margin: 0 0 0.4em;
		font-family: var(--serif);
		font-weight: 400;
		font-size: clamp(2.8rem, 6vw, 5.6rem);
		line-height: 0.95;
		letter-spacing: -0.03em;
		color: var(--red);
	}

	.about :global(p) {
		margin: 0 0 1.2em;
		max-width: 52ch;
		font-weight: 600;
		font-size: 0.95rem;
		line-height: 1.4;
	}

	.about :global(blockquote) {
		margin: 0 0 1em;
		max-width: 26em;
		font-family: var(--serif);
		font-size: clamp(1.6rem, 2.6vw, 2.4rem);
		line-height: 1.1;
		letter-spacing: -0.015em;
	}

	.about :global(p.close) {
		font-weight: 700;
	}

	@media (max-width: 860px) {
		.about-in {
			grid-template-columns: 1fr;
		}
	}
</style>
