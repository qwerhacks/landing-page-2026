<script lang="ts">
	export let setTab: (
		tab:
			| 'application'
			| 'schedule'
			| 'volunteer'
			| 'about'
			| 'info'
			| 'sponsors'
			| 'rsvp'
			| 'theme-and-tracks'
	) => void;
</script>

<div class="space-y-20 py-16 px-4">

	<!-- SECTION 1: HERO -->
	<section class="max-w-5xl mx-auto text-center" aria-labelledby="info-hero-title">
		<div class="glass-card p-10">
			<h1
				id="info-hero-title"
				class="text-4xl md:text-6xl mb-6"
				style="
					font-family: 'Ranille Normal', serif;
					color: #C5A059;
					text-shadow: 0 0 12px rgba(197, 160, 89, 0.45);
				"
			>
				🌈⏱️ 2026 Hackathon Info 🐕🌈
			</h1>

			<p
				class="text-lg md:text-xl max-w-3xl mx-auto"
				style="font-family: 'Spectral', serif;"
			>
				We’re so excited to see you at QWER Hacks!!
			</p>

			<p
				class="text-lg mt-2"
				style="font-family: 'Spectral', serif;"
			>
				Here’s some more information and frequently asked questions ☝️💥🧠
			</p>
		</div>
	</section>

	<!-- SECTION 2: QUICK INFO -->
	<section class="max-w-6xl mx-auto grid md:grid-cols-3 gap-8" aria-label="Event Details">
		<div class="glass-card p-8 md:translate-y-6 text-center">
			<h2 class="card-title">When</h2>
			<p class="card-text">
				February 7–8, 2026
			</p>
		</div>

		<div class="glass-card p-8 text-center">
			<h2 class="card-title">Where</h2>
			<p class="card-text">
				UCLA’s Carnesale Commons
			</p>
		</div>

		<div class="glass-card p-8 md:-translate-y-6 text-center">
			<h2 class="card-title">Cost</h2>
			<p class="card-text">
				It’s free, babey!
			</p>
		</div>
	</section>

	<!-- SECTION 3: FAQ -->
	<section class="max-w-5xl mx-auto" aria-labelledby="info-faq-title">
		<div class="glass-card p-10">
			<h2
				id="info-faq-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				Frequently Asked Questions
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif;">
				<p>
					<strong>Q: Who can attend QWER Hacks?</strong><br />
					A: Anyone who is 18 or older, a member (or ally) of the LGBTQIA+ community,
					and enrolled in a postsecondary academic institution!
				</p>

				<p>
					<strong>Q: How about travel and transportation?</strong><br />
					A: Unfortunately, due to budget constraints, we will not be able to provide
					travel stipends this year :( However, if you would like to be connected with
					other students traveling from the same area and want assistance with
					finding carpooling, you can include your information in the application form
					or email us directly at
					<a
						href="mailto:qwerhacks@gmail.com"
						class="font-semibold underline"
					>
						qwerhacks@gmail.com
					</a>.
				</p>

				<p>
					<strong>Q: How do teams work?</strong><br />
					A: Teams consist of 1–4 hackers! Each member should submit an application.
					Don’t have a team? No worries — we’ll help you find one at the hackathon!
				</p>

				<p>
					<strong>Q: What if I have no prior experience?</strong><br />
					A: No problem! We welcome hackers of all experience levels and will have
					workshops for beginners.
				</p>

				<p>
					<strong>Q: What are the tracks?</strong><br />
					A: For a sneak peek of the QWER Hacks 2026 tracks,
					<span
						class="underline cursor-pointer"
						on:click={() => setTab('theme-and-tracks')}
					>
						click here!
					</span>
				</p>

				<p>
					<strong>Q: How do I apply?</strong><br />
					A: Link right
					<span
						class="underline cursor-pointer"
						on:click={() => setTab('application')}
					>
						here!
					</span>
				</p>
			</div>
		</div>
	</section>

	<!-- SECTION 4: CTA -->
	<section class="max-w-4xl mx-auto text-center" aria-labelledby="info-cta-title">
		<div class="glass-card p-12">
			<h2
				id="info-cta-title"
				class="text-3xl md:text-4xl mb-4"
				style="font-family: 'Ranille Normal', serif;"
			>
				Come Build With Us
			</h2>

			<p
				class="text-lg mb-8 max-w-2xl mx-auto"
				style="font-family: 'Spectral', serif;"
			>
				Whether this is your first hackathon or your fiftieth —
				if you’re curious, kind, and ready to learn, you belong here.
			</p>

			<button
				type="button"
				class="apply-button inline-block px-14 py-4 text-xl rounded-full cursor-pointer"
				on:click={() => setTab('application')}
				style="font-family: 'Spectral', serif;"
			>
				Apply Now
			</button>

			<p class="mt-4 text-sm opacity-80" style="font-family: 'Spectral', serif;">
				or visit tinyurl.com/qwerhacks26
			</p>
		</div>
	</section>
</div>



<style>
	.glass-card {
		background: rgba(0, 0, 0, 0.25);
		backdrop-filter: blur(14px);
		border: 1px solid rgba(255, 255, 255, 0.12);
		border-radius: 1.25rem;
		box-shadow: 0 6px 40px rgba(0, 0, 0, 0.2);
		color: white;
	}

	.card-title {
		font-family: 'Ranille Normal', serif;
		font-size: 1.75rem;
		margin-bottom: 0.5rem;
		color: #C5A059;
	}

	.card-text {
		font-family: 'Spectral', serif;
		font-size: 1.05rem;
	}

	.apply-button {
		background: linear-gradient(
			to right,
			#C5A059,
			#E6C97A,
			#C5A059
		);
		color: black;
		font-weight: 600;
		background-size: 200% 200%;
		transition: all 0.3s ease;
	}

	.apply-button:hover {
		background-position: 100% 50%;
		transform: translateY(-2px);
		box-shadow: 0 6px 20px rgba(197, 160, 89, 0.4);
	}
</style>
