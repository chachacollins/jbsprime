<script lang="ts">
	import Logo from './Logo.svelte';

	let year = new Date().getFullYear();
</script>

<footer class="footer" id="contact">
	<!-- Floating food illustrations scattered around footer -->
	<div class="float-food fries" aria-hidden="true">
		<svg viewBox="0 0 160 70"><path d="M8 40 L10 22 L135 6 L150 14 L146 32 L24 62 L8 52Z" /><path d="M10 22 L24 40 L146 14" /><path d="M24 40 L24 62" /></svg>
	</div>
	<div class="float-food burger" aria-hidden="true">
		<svg viewBox="0 0 140 130"><path d="M20 50 Q22 8 72 8 Q122 8 124 50Z" /><path d="M14 66 Q30 82 44 66 Q58 82 72 66 Q86 82 100 66 Q114 82 128 66" /><path d="M18 88 H126" /><path d="M20 88 Q22 120 72 120 Q122 120 124 88" /><path d="M46 28 L50 30 M84 24 L88 26 M66 38 L70 40" /></svg>
	</div>
	<div class="float-food drumstick" aria-hidden="true">
		<svg viewBox="0 0 120 80"><path d="M6 50 Q4 18 42 16 Q80 14 90 40 Q94 56 74 62 Q40 68 22 64 Q8 62 6 50Z" /><path d="M84 42 L108 56 M108 46 Q116 48 114 56 Q108 66 102 62" /></svg>
	</div>
	<div class="float-food cocktail" aria-hidden="true">
		<svg viewBox="0 0 80 110"><path d="M6 10 H74 L40 54Z" /><path d="M40 54 V94 M22 100 H58" /><path d="M52 30 L66 4" /><circle cx="26" cy="22" r="0.5" /></svg>
	</div>
	<div class="float-food steak" aria-hidden="true">
		<svg viewBox="0 0 130 100"><path d="M14 52 Q10 14 54 12 Q100 8 118 36 Q130 66 96 84 Q54 98 30 80 Q16 70 14 52Z" /><circle cx="82" cy="46" r="14" /><path d="M30 40 Q40 26 56 28" /></svg>
	</div>

	<!-- Animated ember sparks -->
	<div class="sparks" aria-hidden="true">
		{#each Array(12) as _, i}
			<div class="spark" style="--si:{i};--sx:{Math.random() * 100}%;--sy:{60 + Math.random() * 35}%;--sd:{3 + Math.random() * 5}s;--sdelay:{Math.random() * 4}s"></div>
		{/each}
	</div>

	<!-- Kōwhaiwhai-inspired decorative side borders -->
	<div class="koru-left" aria-hidden="true">
		<svg viewBox="0 0 60 600" preserveAspectRatio="none">
			<path d="M30,0 C28,40 35,80 50,100 C65,120 50,140 35,130 C25,122 30,108 40,112" fill="none" stroke="var(--gold)" stroke-width="2.5" stroke-linecap="round" opacity="0.3"/>
			<path d="M30,150 C28,190 35,230 50,250 C65,270 50,290 35,280 C25,272 30,258 40,262" fill="none" stroke="var(--red)" stroke-width="2.5" stroke-linecap="round" opacity="0.25"/>
			<path d="M30,300 C28,340 35,380 50,400 C65,420 50,440 35,430 C25,422 30,408 40,412" fill="none" stroke="var(--gold)" stroke-width="2.5" stroke-linecap="round" opacity="0.2"/>
			<path d="M30,450 C28,490 35,530 50,550 C65,570 50,590 35,580 C25,572 30,558 40,562" fill="none" stroke="var(--red)" stroke-width="2.5" stroke-linecap="round" opacity="0.15"/>
		</svg>
	</div>
	<div class="koru-right" aria-hidden="true">
		<svg viewBox="0 0 60 600" preserveAspectRatio="none">
			<path d="M30,0 C28,40 35,80 50,100 C65,120 50,140 35,130 C25,122 30,108 40,112" fill="none" stroke="var(--gold)" stroke-width="2.5" stroke-linecap="round" opacity="0.3"/>
			<path d="M30,150 C28,190 35,230 50,250 C65,270 50,290 35,280 C25,272 30,258 40,262" fill="none" stroke="var(--red)" stroke-width="2.5" stroke-linecap="round" opacity="0.25"/>
			<path d="M30,300 C28,340 35,380 50,400 C65,420 50,440 35,430 C25,422 30,408 40,412" fill="none" stroke="var(--gold)" stroke-width="2.5" stroke-linecap="round" opacity="0.2"/>
			<path d="M30,450 C28,490 35,530 50,550 C65,570 50,590 35,580 C25,572 30,558 40,562" fill="none" stroke="var(--red)" stroke-width="2.5" stroke-linecap="round" opacity="0.15"/>
		</svg>
	</div>

	<div class="footer-inner">
		<!-- Big bold footer headline -->
		<div class="footer-hero">
			<h2 class="footer-headline">
				Come hungry.<br/>
				<span class="italic-accent">Leave happy.</span>
			</h2>
	
		</div>

		<!-- Main grid -->
		<div class="footer-grid">
			<!-- Brand column -->
			<div class="footer-brand">
				<div class="brand-logo">
					<Logo href="#top" label="JB's Prime Grill & Lounge" />
				</div>
				<p class="brand-tagline">
					Great food, fine drinks and a place for exceptional moments. Opening soon at Waris Mall on the Eastern Bypass.
				</p>
			</div>

			<!-- Contact -->
			<div class="footer-col">
				<h4 class="col-title">Contact</h4>
				<address class="contact-info">
					<p class="address-line">
						<!-- Map pin icon -->
						<svg class="contact-icon" viewBox="0 0 24 24" aria-hidden="true">
							<path d="M12,2 C8.13,2 5,5.13 5,9 C5,14.25 12,22 12,22 C12,22 19,14.25 19,9 C19,5.13 15.87,2 12,2Z" fill="none" stroke="currentColor" stroke-width="1.5"/>
							<circle cx="12" cy="9" r="2.5" fill="none" stroke="currentColor" stroke-width="1.5"/>
						</svg>
						Waris Mall, Eastern Bypass,<br/>off Ruai–Kandundo Road Junction
					</p>
					<p>
						<svg class="contact-icon" viewBox="0 0 24 24" aria-hidden="true">
							<path d="M22,16.92V19.92C22,20.48 21.56,20.93 21,20.95C14.07,21.5 7.74,18.03 4.03,12.47C2.19,9.72 1.37,6.5 1.95,3.08C2,2.52 2.44,2.07 3,2.05H6C6.46,2.03 6.87,2.33 6.97,2.78C7.35,4.41 7.98,5.98 8.82,7.42L6.79,9.45C8.44,12.38 10.62,14.56 13.55,16.21L15.58,14.18C17.02,15.02 18.59,15.65 20.22,16.03C20.67,16.13 20.97,16.54 20.95,17L22,16.92Z" fill="none" stroke="currentColor" stroke-width="1.5"/>
						</svg>
						<a href="tel:0185504008" class="contact-link">0185 504 008</a>
					</p>
					<p>
						<svg class="contact-icon" viewBox="0 0 24 24" aria-hidden="true">
							<rect x="2" y="4" width="20" height="16" rx="2" fill="none" stroke="currentColor" stroke-width="1.5"/>
							<path d="M22,4 L12,13 L2,4" fill="none" stroke="currentColor" stroke-width="1.5"/>
						</svg>
						<a href="mailto:info@jbsprime.co.ke" class="contact-link">info@jbsprime.co.ke</a>
					</p>
				</address>
			</div>

			<!-- Hours -->
			<div class="footer-col">
				<h4 class="col-title">Hours</h4>
				<div class="hours-info">
					<div class="hours-row">
						<span class="day">Monday – Sunday</span>
						<span class="time">6:00 am – 11:00 pm</span>
					</div>
					<div class="hours-divider"></div>
					<p class="hours-note">
						<svg class="note-icon" viewBox="0 0 24 24" aria-hidden="true">
							<circle cx="12" cy="12" r="10" fill="none" stroke="var(--gold)" stroke-width="1.5"/>
							<path d="M12,8 L12,12 L15,15" fill="none" stroke="var(--gold)" stroke-width="1.5" stroke-linecap="round"/>
						</svg>
						Lounge service is available by booking
					</p>
				</div>
				<!-- CTA pill -->
				<a href="https://www.google.com/maps/dir/?api=1&destination=Waris+Mall,+Eastern+Bypass,+Ruai" class="footer-cta" id="directions" target="_blank" rel="noopener noreferrer">
					Get Directions
					<svg viewBox="0 0 24 24" class="arrow-icon" aria-hidden="true">
						<path d="M5,12 H19 M13,6 L19,12 L13,18" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
					</svg>
				</a>
			</div>
		</div>

		<!-- Bottom bar -->
		<div class="footer-bottom">
			<div class="bottom-left">
				<span class="copyright">
					&copy; {year} JB'S Prime Grill &amp; Lounge. All rights reserved.
				</span>
			</div>
			<div class="bottom-right">
				<span class="built-by">
					Built with
					<svg class="heart" viewBox="0 0 24 24" aria-hidden="true">
						<path d="M12,21 L10.55,19.7C5.4,15.1 2,12.1 2,8.5C2,5.4 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.09C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.4 22,8.5C22,12.1 18.6,15.1 13.45,19.7L12,21Z" fill="var(--red)"/>
					</svg>
					by <a href="https://chachas.site" class="credit-link" target="_blank" rel="noopener noreferrer">Collins Chacha</a>
				</span>
			</div>
		</div>
	</div>
</footer>

<style>
	.footer {
		position: relative;
		background: var(--bg);
		color: var(--ink);
		padding: 0 clamp(20px, 5vw, 96px) 0;
		overflow: hidden;
	}

	/* =============================================
	   FLOATING FOOD ILLUSTRATIONS
	   ============================================= */
	.float-food {
		position: absolute;
		pointer-events: none;
		z-index: 1;
		will-change: transform;
	}

	.float-food :global(svg) {
		display: block;
		width: 100%;
		height: auto;
		overflow: visible;
	}

	.float-food :global(path),
	.float-food :global(circle),
	.float-food :global(rect),
	.float-food :global(ellipse) {
		fill: none;
		stroke-width: 5;
		stroke-linecap: round;
		stroke-linejoin: round;
	}

	.fries {
		width: 120px;
		top: 8%;
		right: 6%;
		animation: float-a 8s ease-in-out infinite alternate;
		opacity: 0.18;
	}
	.fries :global(*) { stroke: var(--gold); }

	.burger {
		width: 100px;
		bottom: 28%;
		right: 3%;
		animation: float-b 9s ease-in-out -3s infinite alternate;
		opacity: 0.14;
	}
	.burger :global(*) { stroke: var(--red); }

	.drumstick {
		width: 90px;
		top: 55%;
		left: 2%;
		animation: float-a 7s ease-in-out -2s infinite alternate;
		opacity: 0.15;
	}
	.drumstick :global(*) { stroke: var(--gold); }

	.cocktail {
		width: 55px;
		top: 15%;
		left: 8%;
		animation: float-b 6s ease-in-out -1s infinite alternate;
		opacity: 0.2;
	}
	.cocktail :global(*) { stroke: var(--red); }

	.steak {
		width: 80px;
		bottom: 12%;
		left: 12%;
		animation: float-a 10s ease-in-out -4s infinite alternate;
		opacity: 0.12;
	}
	.steak :global(*) { stroke: var(--ink); }

	@keyframes float-a {
		0%   { transform: translate3d(0, 0, 0) rotate(-6deg); }
		50%  { transform: translate3d(14px, -18px, 0) rotate(4deg); }
		100% { transform: translate3d(-10px, 12px, 0) rotate(-8deg); }
	}

	@keyframes float-b {
		0%   { transform: translate3d(0, 0, 0) rotate(5deg); }
		50%  { transform: translate3d(-12px, -14px, 0) rotate(-6deg); }
		100% { transform: translate3d(16px, 10px, 0) rotate(8deg); }
	}

	/* =============================================
	   EMBER SPARKS
	   ============================================= */
	.sparks {
		position: absolute;
		inset: 0;
		pointer-events: none;
		z-index: 1;
		overflow: hidden;
	}

	.spark {
		position: absolute;
		width: 4px;
		height: 4px;
		border-radius: 50%;
		background: var(--gold);
		left: var(--sx);
		top: var(--sy);
		opacity: 0;
		animation: rise var(--sd) ease-out var(--sdelay) infinite;
	}

	.spark:nth-child(odd) {
		background: var(--red);
		width: 3px;
		height: 3px;
	}

	@keyframes rise {
		0% {
			opacity: 0;
			transform: translateY(0) scale(0.5);
		}
		15% {
			opacity: 0.8;
		}
		100% {
			opacity: 0;
			transform: translateY(-120px) translateX(20px) scale(0);
		}
	}

	/* =============================================
	   KŌWHAIWHAI SIDE BORDERS
	   ============================================= */
	.koru-left,
	.koru-right {
		position: absolute;
		top: 0;
		width: 40px;
		height: 100%;
		pointer-events: none;
		z-index: 1;
	}

	.koru-left {
		left: clamp(4px, 1vw, 16px);
	}

	.koru-right {
		right: clamp(4px, 1vw, 16px);
		transform: scaleX(-1);
	}

	.koru-left svg,
	.koru-right svg {
		width: 100%;
		height: 100%;
	}

	/* =============================================
	   FOOTER HERO HEADLINE
	   ============================================= */
	.footer-hero {
		position: relative;
		z-index: 2;
		text-align: center;
		padding: clamp(48px, 7vw, 96px) 0 clamp(32px, 4vw, 56px);
	}

	.footer-headline {
		font-family: var(--serif);
		font-weight: 400;
		font-size: clamp(2.8rem, 7vw, 6.5rem);
		line-height: 0.95;
		letter-spacing: -0.03em;
		margin: 0;
		color: var(--ink);
		text-transform: uppercase;
	}

	.italic-accent {
		font-style: italic;
		color: var(--red);
	}

/* =============================================
	   INNER CONTAINER
	   ============================================= */
	.footer-inner {
		position: relative;
		z-index: 2;
		max-width: 1400px;
		margin: 0 auto;
	}

	/* =============================================
	   GRID
	   ============================================= */
	.footer-grid {
		display: grid;
		grid-template-columns: 1.4fr 1fr 1fr;
		gap: clamp(28px, 4vw, 64px);
		padding-bottom: clamp(40px, 5vw, 64px);
	}

	/* =============================================
	   BRAND COLUMN
	   ============================================= */
	.footer-brand {
		padding-right: clamp(16px, 2vw, 32px);
	}

	.brand-logo {
		margin-bottom: 20px;
	}

	.brand-tagline {
		margin: 0;
		font-weight: 400;
		font-size: 0.85rem;
		line-height: 1.6;
		opacity: 0.75;
	}

	/* =============================================
	   COLUMN TITLES
	   ============================================= */
	.col-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(1.3rem, 1.8vw, 1.6rem);
		margin: 0 0 clamp(16px, 2vw, 24px);
		color: var(--red);
		letter-spacing: -0.01em;
	}

	/* =============================================
	   CONTACT INFO
	   ============================================= */
	address {
		font-style: normal;
	}

	.contact-info p {
		display: flex;
		align-items: flex-start;
		gap: 10px;
		margin: 0 0 14px;
		font-weight: 600;
		font-size: 0.82rem;
		line-height: 1.55;
		letter-spacing: 0.02em;
		text-transform: uppercase;
		opacity: 0.75;
	}

	.contact-icon {
		width: 18px;
		height: 18px;
		flex-shrink: 0;
		margin-top: 1px;
		color: var(--gold);
	}

	.contact-link {
		color: var(--ink);
		text-decoration: none;
		border-bottom: 1px solid transparent;
		transition: border-color 0.25s, color 0.25s;
	}

	.contact-link:hover {
		border-bottom-color: var(--gold);
		color: var(--gold);
	}

	.address-line {
		line-height: 1.6 !important;
	}

	/* =============================================
	   HOURS
	   ============================================= */
	.hours-info {
		margin-bottom: 24px;
	}

	.hours-row {
		display: flex;
		flex-direction: column;
		gap: 2px;
	}

	.day {
		font-weight: 700;
		font-size: 0.82rem;
		letter-spacing: 0.03em;
		text-transform: uppercase;
	}

	.time {
		font-family: var(--serif);
		font-style: italic;
		font-size: 1.1rem;
		color: var(--gold);
		letter-spacing: -0.01em;
	}

	.hours-divider {
		width: 40px;
		height: 1.5px;
		background: var(--red);
		margin: 16px 0;
		opacity: 0.5;
	}

	.hours-note {
		display: flex;
		align-items: center;
		gap: 8px;
		margin: 0;
		font-size: 0.78rem;
		font-weight: 600;
		letter-spacing: 0.02em;
		text-transform: uppercase;
		opacity: 0.6;
	}

	.note-icon {
		width: 16px;
		height: 16px;
		flex-shrink: 0;
	}

	/* =============================================
	   CTA BUTTON — oval pill matching hero style
	   ============================================= */
	.footer-cta {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: 10px;
		width: 240px;
		height: 80px;
		border: 1px solid var(--ink);
		border-color: var(--red);
		border-radius: 50%;
		font-weight: 700;
		font-size: 0.82rem;
		letter-spacing: 0.06em;
		text-transform: uppercase;
		color: var(--red);
		margin-top: 24px;
		transition: background 0.25s, color 0.25s, transform 0.3s, box-shadow 0.3s;
	}

	.footer-cta:hover {
		background: var(--red);
		color: var(--bg);
		transform: translateY(-3px);
		box-shadow: 0 8px 30px rgba(255, 59, 71, 0.35);
	}

	.arrow-icon {
		width: 18px;
		height: 18px;
		transition: transform 0.3s;
	}

	.footer-cta:hover .arrow-icon {
		transform: translateX(6px);
	}

	/* =============================================
	   BOTTOM BAR
	   ============================================= */
	.footer-bottom {
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
		gap: 16px;
		padding: clamp(20px, 3vw, 32px) 0;
		border-top: 1px solid rgba(247, 243, 238, 0.12);
	}

	.copyright {
		font-size: 0.72rem;
		font-weight: 400;
		letter-spacing: 0.02em;
		opacity: 0.4;
	}

	.built-by {
		display: inline-flex;
		align-items: center;
		gap: 5px;
		font-size: 0.72rem;
		font-weight: 400;
		letter-spacing: 0.02em;
		opacity: 0.5;
		transition: opacity 0.3s;
	}

	.built-by:hover {
		opacity: 0.9;
	}

	.heart {
		width: 14px;
		height: 14px;
		animation: heartbeat 1.8s ease-in-out infinite;
	}

	@keyframes heartbeat {
		0%, 100% { transform: scale(1); }
		14% { transform: scale(1.3); }
		28% { transform: scale(1); }
		42% { transform: scale(1.2); }
		56% { transform: scale(1); }
	}

	.credit-link {
		color: var(--gold);
		font-weight: 700;
		text-decoration: none;
		border-bottom: 1px solid transparent;
		transition: border-color 0.25s;
	}

	.credit-link:hover {
		border-bottom-color: var(--gold);
	}

	/* =============================================
	   RESPONSIVE
	   ============================================= */
	@media (max-width: 960px) {
		.footer-grid {
			grid-template-columns: 1fr 1fr;
			gap: clamp(28px, 5vw, 48px);
		}

		.footer-brand {
			grid-column: 1 / -1;
			padding-right: 0;
		}

		.fries,
		.steak { display: none; }
	}

	@media (max-width: 600px) {
		.footer-grid {
			grid-template-columns: 1fr;
		}

		.footer-cta {
			width: 200px;
			height: 68px;
			font-size: 0.8rem;
		}

		.footer-bottom {
			flex-direction: column;
			align-items: flex-start;
		}

		.float-food { display: none; }

		.koru-left,
		.koru-right { display: none; }

		.footer-headline {
			font-size: clamp(2.2rem, 10vw, 3.6rem);
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.float-food,
		.spark {
			animation: none !important;
		}
		.float-food {
			opacity: 0.1 !important;
		}
		.spark {
			display: none;
		}
	}
</style>
