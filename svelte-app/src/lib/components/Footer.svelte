<script lang="ts">
	import Logo from './Logo.svelte';

	const quickLinks = [
		{ href: '#about', label: 'What We Do' },
		{ href: '#about', label: 'Our Story' },
		{ href: '#top', label: 'Visit Us' }
	];

	let year = new Date().getFullYear();
</script>

<footer class="footer" id="contact">
	<div class="footer-inner">
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
				<!-- Decorative flame divider -->
				<div class="mini-flame" aria-hidden="true">
					<svg viewBox="0 0 80 24">
						<path d="M10,22 Q12,16 14,10 Q16,4 18,8 Q20,2 22,8 Q24,4 26,10 Q28,16 30,22" fill="none" stroke="var(--red)" stroke-width="1.5" stroke-linecap="round"/>
						<path d="M34,22 Q36,14 38,8 Q40,2 42,8 Q44,14 46,22" fill="none" stroke="var(--gold)" stroke-width="1.5" stroke-linecap="round"/>
						<path d="M50,22 Q52,16 54,10 Q56,4 58,8 Q60,2 62,8 Q64,4 66,10 Q68,16 70,22" fill="none" stroke="var(--red)" stroke-width="1.5" stroke-linecap="round"/>
					</svg>
				</div>
			</div>

			<!-- Quick Links -->
			<div class="footer-col">
				<h4 class="col-title">Quick Links</h4>
				<ul class="link-list">
					{#each quickLinks as link}
						<li><a href={link.href}>{link.label}</a></li>
					{/each}
				</ul>
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
				<a href="#directions" class="footer-cta" id="directions">
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
					by <a href="https://collinschacha.com" class="credit-link" target="_blank" rel="noopener noreferrer">Collins Chacha</a>
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
		padding: clamp(40px, 6vw, 72px) clamp(20px, 5vw, 96px) 0;
		overflow: hidden;
	}

	/* Inner container */
	.footer-inner {
		max-width: 1400px;
		margin: 0 auto;
	}

	/* Grid */
	.footer-grid {
		display: grid;
		grid-template-columns: 1.4fr 0.8fr 1fr 1fr;
		gap: clamp(28px, 4vw, 64px);
		padding-bottom: clamp(40px, 5vw, 64px);
	}

	/* Brand column */
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

	.mini-flame {
		margin-top: 24px;
		width: 80px;
		opacity: 0.6;
	}

	.mini-flame svg {
		display: block;
		width: 100%;
		height: auto;
	}

	/* Column titles */
	.col-title {
		font-family: var(--serif);
		font-weight: 400;
		font-style: italic;
		font-size: clamp(1.3rem, 1.8vw, 1.6rem);
		margin: 0 0 clamp(16px, 2vw, 24px);
		color: var(--red);
		letter-spacing: -0.01em;
	}

	/* Quick links */
	.link-list {
		list-style: none;
		margin: 0;
		padding: 0;
	}

	.link-list li {
		margin-bottom: 0;
	}

	.link-list a {
		display: inline-block;
		padding: 7px 0;
		font-weight: 600;
		font-size: 0.82rem;
		letter-spacing: 0.03em;
		text-transform: uppercase;
		color: var(--ink);
		opacity: 0.7;
		transition: opacity 0.25s, transform 0.25s;
		position: relative;
	}

	.link-list a::after {
		content: '';
		position: absolute;
		left: 0;
		bottom: 4px;
		width: 0;
		height: 1.5px;
		background: var(--gold);
		transition: width 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
	}

	.link-list a:hover {
		opacity: 1;
		transform: translateX(4px);
	}

	.link-list a:hover::after {
		width: 100%;
	}

	/* Contact info */
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
		transition: border-color 0.25s;
	}

	.contact-link:hover {
		border-bottom-color: var(--gold);
	}

	.address-line {
		line-height: 1.6 !important;
	}

	/* Hours */
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

	/* CTA button */
	.footer-cta {
		display: inline-flex;
		align-items: center;
		gap: 10px;
		padding: 14px 28px;
		border: 1.5px solid var(--red);
		border-radius: 99px;
		font-weight: 700;
		font-size: 0.78rem;
		letter-spacing: 0.06em;
		text-transform: uppercase;
		color: var(--red);
		transition: background 0.3s, color 0.3s, transform 0.3s;
	}

	.footer-cta:hover {
		background: var(--red);
		color: var(--bg);
		transform: translateY(-2px);
	}

	.arrow-icon {
		width: 18px;
		height: 18px;
		transition: transform 0.3s;
	}

	.footer-cta:hover .arrow-icon {
		transform: translateX(4px);
	}

	/* Bottom bar */
	.footer-bottom {
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
		gap: 16px;
		padding: clamp(20px, 3vw, 32px) 0;
		border-top: 1px solid rgba(247, 243, 238, 0.1);
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
		14% { transform: scale(1.2); }
		28% { transform: scale(1); }
		42% { transform: scale(1.15); }
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

	/* Responsive */
	@media (max-width: 960px) {
		.footer-grid {
			grid-template-columns: 1fr 1fr;
			gap: clamp(28px, 5vw, 48px);
		}

		.footer-brand {
			grid-column: 1 / -1;
			padding-right: 0;
		}
	}

	@media (max-width: 600px) {
		.footer-grid {
			grid-template-columns: 1fr;
		}

		.footer-bottom {
			flex-direction: column;
			align-items: flex-start;
		}
	}
</style>
