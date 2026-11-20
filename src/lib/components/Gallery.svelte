<script lang="ts">
	interface GalleryImage {
		src: string;
		alt: string;
		rotation: number;
	}

	const images: GalleryImage[] = [
		{ src: '/gallery/image1.jpeg', alt: 'Gallery photo 1', rotation: -3 },
		{ src: '/gallery/image2.jpeg', alt: 'Gallery photo 2', rotation: 2 },
		{ src: '/gallery/image3.jpeg', alt: 'Gallery photo 3', rotation: -4 },
		{ src: '/gallery/image4.jpeg', alt: 'Gallery photo 4', rotation: 3 },
		{ src: '/gallery/image5.jpeg', alt: 'Gallery photo 5', rotation: -2 },
		{ src: '/gallery/image6.jpeg', alt: 'Gallery photo 6', rotation: 4 },
		{ src: '/gallery/image7.jpeg', alt: 'Gallery photo 7', rotation: -3 },
	];

	// Duplicate for seamless loop
	const allImages = [...images, ...images];

	let selectedImage: string | null = $state(null);
	let isPaused = $state(false);

	function openImage(src: string) {
		selectedImage = src;
	}

	function closeImage() {
		selectedImage = null;
	}

	function handleKeydown(e: KeyboardEvent) {
		if (e.key === 'Escape' && selectedImage) {
			closeImage();
		}
	}
</script>

<svelte:window onkeydown={handleKeydown} />

<section class="gallery" id="gallery">
	<h2>Gallery</h2>

	<div
		class="carousel-track-wrapper"
		role="region"
		aria-label="Image gallery carousel"
	>
		<div
			class="carousel-track"
			class:paused={isPaused}
		>
			{#each allImages as image, i}
				<button
					class="carousel-card"
					style="--rotation: {image.rotation}deg"
					onclick={() => openImage(image.src)}
					onmouseenter={() => isPaused = true}
					onmouseleave={() => isPaused = false}
					aria-label="View {image.alt}"
				>
					<img
						src={image.src}
						alt={image.alt}
						loading="lazy"
						draggable="false"
					/>
				</button>
			{/each}
		</div>
	</div>
</section>

{#if selectedImage}
	<div
		class="lightbox"
		onclick={closeImage}
		onkeydown={(e) => e.key === 'Escape' && closeImage()}
		role="dialog"
		aria-modal="true"
		aria-label="Enlarged view"
		tabindex="-1"
	>
		<button class="lightbox-close" onclick={closeImage} aria-label="Close">✕</button>
		<button class="lightbox-content" onclick={(e) => e.stopPropagation()} type="button" aria-label="Enlarged photo">
			<img src={selectedImage} alt="Gallery photo enlarged" />
		</button>
	</div>
{/if}

<style>
	.gallery {
		background: #f7f3ee;
		padding: clamp(48px, 8vw, 100px) 0;
		overflow: hidden;
	}

	h2 {
		text-align: center;
		font-family: var(--serif);
		font-weight: 400;
		font-size: clamp(2.8rem, 6vw, 5.6rem);
		line-height: 0.95;
		letter-spacing: -0.03em;
		color: var(--red);
		margin: 0 0 clamp(32px, 5vw, 60px);
	}

	.carousel-track-wrapper {
		width: 100%;
		overflow: hidden;
		padding: 40px 0;
	}

	.carousel-track {
		display: flex;
		gap: clamp(20px, 3vw, 40px);
		width: max-content;
		animation: scroll 35s linear infinite;
	}

	.carousel-track.paused {
		animation-play-state: paused;
	}

	@keyframes scroll {
		0% {
			transform: translateX(0);
		}
		100% {
			transform: translateX(-50%);
		}
	}

	.carousel-card {
		flex-shrink: 0;
		width: clamp(220px, 22vw, 340px);
		aspect-ratio: 3 / 4;
		border-radius: 20px;
		overflow: hidden;
		box-shadow: 0 16px 40px rgba(60, 10, 15, 0.2);
		transform: rotate(var(--rotation));
		transition:
			transform 0.4s cubic-bezier(0.2, 0.8, 0.2, 1),
			box-shadow 0.4s ease;
		cursor: pointer;
		border: none;
		padding: 0;
		background: none;
		position: relative;
	}

	.carousel-card:hover {
		transform: rotate(0deg) translateY(-16px) scale(1.04);
		box-shadow: 0 24px 56px rgba(60, 10, 15, 0.32);
		z-index: 2;
	}

	.carousel-card:focus-visible {
		outline: 3px solid var(--gold);
		outline-offset: 4px;
	}

	.carousel-card img {
		display: block;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	/* Lightbox */
	.lightbox {
		position: fixed;
		inset: 0;
		background: rgba(0, 0, 0, 0.85);
		z-index: 1000;
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
		animation: fadeIn 0.25s ease;
	}

	@keyframes fadeIn {
		from { opacity: 0; }
		to { opacity: 1; }
	}

	.lightbox-close {
		position: absolute;
		top: 20px;
		right: 24px;
		background: none;
		border: none;
		color: white;
		font-size: 2rem;
		cursor: pointer;
		z-index: 1001;
		line-height: 1;
		padding: 8px;
		transition: transform 0.2s ease;
	}

	.lightbox-close:hover {
		transform: scale(1.2);
	}

	.lightbox-content {
		cursor: default;
		max-width: 90vw;
		max-height: 90vh;
		animation: scaleIn 0.3s cubic-bezier(0.2, 0.8, 0.2, 1);
		background: none;
		border: none;
		padding: 0;
	}

	@keyframes scaleIn {
		from {
			transform: scale(0.9);
			opacity: 0;
		}
		to {
			transform: scale(1);
			opacity: 1;
		}
	}

	.lightbox-content img {
		max-width: 90vw;
		max-height: 90vh;
		object-fit: contain;
		border-radius: 16px;
		box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
	}

	@media (prefers-reduced-motion: reduce) {
		.carousel-track {
			animation: none;
		}
		.carousel-card {
			transition: none;
		}
	}
</style>
