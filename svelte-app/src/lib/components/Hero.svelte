<script lang="ts">
	import Nav from './Nav.svelte';
	import FloatingFood from './FloatingFood.svelte';

	const navLinks = [
		{ href: '#about', label: 'About us' },
		{ href: '#menu', label: 'Menu' },
		{ href: '#contact', label: 'Contact' },
		{ href: 'https://www.google.com/maps/dir/?api=1&destination=Waris+Mall,+Eastern+Bypass,+Ruai', label: 'Directions' }
	];
</script>

<header class="hero" id="top">
	<Nav links={navLinks} />

	<div class="center">
		<h1>JB's Prime</h1>
		<p class="tag">Grill <span style="font-size:.8em">&amp;</span> Lounge</p>
		<p class="lead">
			Fire-grilled, juicy and unapologetically good. Pull up a seat at JB's and taste why our
			guests keep coming back.
		</p>
	</div>

	<div class="cta">
		<a class="btn red" href="https://www.google.com/maps/dir/?api=1&destination=Waris+Mall,+Eastern+Bypass,+Ruai" target="_blank" rel="noopener noreferrer">Get directions</a>
		<a class="btn white" href="#menu">View the menu</a>
	</div>

	<div class="corner l">
		JB's Prime Grill &amp; Lounge<span>Waris Mall, Eastern Bypass,</span>
	</div>
	<div class="corner r">Since 2026</div>

	<!-- Fries (gold) -->
	<FloatingFood x="26%" y="25%" w="150px" d="7s" dx="18px" dy="22px" r="8deg" sd="6s" color="gold" top>
		<svg viewBox="0 0 160 70"><path d="M8 40 L10 22 L135 6 L150 14 L146 32 L24 62 L8 52Z" /><path d="M10 22 L24 40 L146 14" /><path d="M24 40 L24 62" /></svg>
	</FloatingFood>
	<FloatingFood x="60%" y="17%" w="100px" d="6s" dx="-14px" dy="18px" r="10deg" sd="5s" delay="-2s" color="gold">
		<svg viewBox="0 0 160 70"><path d="M8 40 L10 22 L135 6 L150 14 L146 32 L24 62 L8 52Z" /><path d="M10 22 L24 40 L146 14" /><path d="M24 40 L24 62" /></svg>
	</FloatingFood>
	<FloatingFood x="73%" y="55%" w="140px" d="8s" dx="16px" dy="20px" r="12deg" sd="7s" delay="-3s" color="gold" top>
		<svg viewBox="0 0 160 70"><path d="M8 40 L10 22 L135 6 L150 14 L146 32 L24 62 L8 52Z" /><path d="M10 22 L24 40 L146 14" /><path d="M24 40 L24 62" /></svg>
	</FloatingFood>
	<FloatingFood x="18%" y="64%" w="46px" d="5s" dx="10px" dy="14px" r="15deg" sd="4s" delay="-1s" color="gold" hideOnMobile>
		<svg viewBox="0 0 160 70"><path d="M8 40 L10 22 L135 6 L150 14 L146 32 L24 62 L8 52Z" /><path d="M10 22 L24 40 L146 14" /></svg>
	</FloatingFood>

	<!-- Fry cone (red) -->
	<FloatingFood x="-1%" y="46%" w="150px" d="9s" dx="12px" dy="24px" r="6deg" sd="8s" delay="-4s" color="red">
		<svg viewBox="0 0 120 120"><path d="M8 60 L50 40 L84 66 L40 100 Q8 108 8 82Z" /><path d="M52 40 L58 14 M64 44 L70 12 M76 52 L90 20 M86 62 L108 40" /><path d="M52 40 Q70 70 84 66 M30 66 L60 88" /></svg>
	</FloatingFood>

	<!-- Burger (red) -->
	<FloatingFood x="87%" y="80%" w="150px" d="8s" dx="-10px" dy="-18px" r="7deg" sd="6s" delay="-2s" color="red">
		<svg viewBox="0 0 140 130"><path d="M20 50 Q22 8 72 8 Q122 8 124 50Z" /><path d="M14 66 Q30 82 44 66 Q58 82 72 66 Q86 82 100 66 Q114 82 128 66" /><path d="M18 88 H126" /><path d="M20 88 Q22 120 72 120 Q122 120 124 88" /><path d="M46 28 L50 30 M84 24 L88 26 M66 38 L70 40" /></svg>
	</FloatingFood>

	<!-- Steak (white) -->
	<FloatingFood x="8%" y="16%" w="110px" d="10s" dx="14px" dy="20px" r="9deg" sd="9s" delay="-5s" color="white" hideOnMobile>
		<svg viewBox="0 0 130 100"><path d="M14 52 Q10 14 54 12 Q100 8 118 36 Q130 66 96 84 Q54 98 30 80 Q16 70 14 52Z" /><circle cx="82" cy="46" r="14" /><path d="M30 40 Q40 26 56 28" /></svg>
	</FloatingFood>

	<!-- Cocktail (red) -->
	<FloatingFood x="82%" y="30%" w="70px" d="7s" dx="-12px" dy="20px" r="12deg" sd="6s" delay="-3s" color="red" hideOnMobile>
		<svg viewBox="0 0 80 110"><path d="M6 10 H74 L40 54Z" /><path d="M40 54 V94 M22 100 H58" /><path d="M52 30 L66 4" /><circle cx="26" cy="22" r="0.5" /></svg>
	</FloatingFood>

	<!-- Drumstick (gold) -->
	<FloatingFood x="42%" y="80%" w="90px" d="6.5s" dx="12px" dy="-16px" r="14deg" sd="5s" delay="-1.5s" color="gold" hideOnMobile>
		<svg viewBox="0 0 120 80"><path d="M6 50 Q4 18 42 16 Q80 14 90 40 Q94 56 74 62 Q40 68 22 64 Q8 62 6 50Z" /><path d="M84 42 L108 56 M108 46 Q116 48 114 56 Q108 66 102 62" /></svg>
	</FloatingFood>
</header>

<style>
	.hero {
		position: relative;
		height: 100vh;
		height: 100svh;
		min-height: 560px;
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	.center {
		position: relative;
		z-index: 3;
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;
		padding: 0 20px;
	}

	h1 {
		margin: 0;
		font-family: var(--serif);
		font-weight: 400;
		font-size: clamp(3rem, 10.5vw, 10.5rem);
		line-height: 0.9;
		letter-spacing: -0.035em;
		color: var(--ink);
		text-transform: uppercase;
	}

	.tag {
		margin: 0.1em 0 0;
		font-family: var(--serif);
		font-style: italic;
		font-size: clamp(2.6rem, 9vw, 9rem);
		line-height: 0.9;
		letter-spacing: -0.03em;
		color: var(--red);
	}

	.lead {
		max-width: 34ch;
		margin: clamp(24px, 4vw, 56px) auto 0;
		font-weight: 600;
		font-size: clamp(0.8rem, 1.1vw, 0.95rem);
		line-height: 1.35;
		text-transform: uppercase;
	}

	.cta {
		position: relative;
		z-index: 4;
		display: flex;
		justify-content: center;
		gap: 32px;
		flex-wrap: wrap;
		padding: 0 20px clamp(24px, 5vh, 56px);
	}

	.btn {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		width: 280px;
		height: 90px;
		border-radius: 50%;
		border: 1px solid var(--ink);
		font-weight: 700;
		font-size: 0.95rem;
		letter-spacing: 0.06em;
		text-transform: uppercase;
		transition:
			background 0.25s,
			color 0.25s;
	}

	.btn.red {
		border-color: var(--red);
		color: var(--red);
	}

	.btn.red:hover {
		background: var(--red);
		color: var(--bg);
	}

	.btn.white:hover {
		background: var(--ink);
		color: var(--bg);
	}

	.corner {
		position: absolute;
		bottom: clamp(20px, 4vh, 40px);
		z-index: 4;
		font-size: 0.85rem;
		line-height: 1.3;
		text-transform: uppercase;
	}

	.corner.l {
		left: clamp(20px, 5vw, 96px);
		font-weight: 600;
	}

	.corner.l span {
		font-weight: 400;
		display: block;
	}

	.corner.r {
		right: clamp(20px, 5vw, 96px);
	}

	@media (max-width: 760px) {
		.btn {
			width: 200px;
			height: 68px;
			font-size: 0.8rem;
		}

		.cta {
			gap: 14px;
		}

		.corner.r {
			display: none;
		}
	}
</style>
