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

	<img src="/astronaut_dog.png" alt="Astronaut Dog (spacer)" class="astronaut-dog" />

	<!-- SECTION 4: GUIDE HERO -->
	<section class="max-w-5xl mx-auto text-center" aria-labelledby="guide-hero-title">
		<div class="glass-card p-10">
			<h1
				id="guide-hero-title"
				class="text-4xl md:text-6xl mb-6"
				style="
					font-family: 'Ranille Normal', serif;
					color: #C5A059;
					text-shadow: 0 0 12px rgba(197, 160, 89, 0.45);
				"
			>
				🌈⏱️ QWER Hacks Guide 🐕🌈
			</h1>

			<p
				class="text-lg mt-2"
				style="font-family: 'Spectral', serif;"
			>
				Here's our guide for what YOU need to know on the day of! ☝️💥🧠
			</p>
		</div>
	</section>

	<!-- SECTION 4: CHECK-IN -->
	<section class="max-w-5xl mx-auto" aria-labelledby="check-in-title">
		<div class="glass-card p-10">
			<h2
				id="check-in-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				Check-in
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif;">
				<p>			
					Check-in starts at <strong>9AM, February 7th, 2026</strong>, and will be open until <strong>10AM</strong>,
					so make sure to be there before then! (If you can’t make it then – please let us know and we will accommodate you.)
				</p>
				<p>
					We will be in the lobby of the Palisades Room at Carnesale Commons, above BPlate. Don't worry about getting lost :)
					We have maps and directions here for you to reference.
				</p>
			</div>
		</div>
	</section>

	<!-- SECTION 5: MAPS AND DIRECTIONS -->
	 <section class="max-w-5xl mx-auto" aria-labelledby="directions-title">
		<div class="glass-card p-10">
			<h2
				id="directions-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				Maps and Directions 🗺️
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; padding:15px;">
				<ul style="list-style-type:disc;">
					<li>
						The hackathon is located in the Palisades Room on the third floor of Carnesale Commons—right above BPlate!
						This is where check-in and hacking will take place.
					</li>
					<li>
						Carnesale Commons is at <strong>251 Charles E Young Drive West, Los Angeles, CA 90095</strong>
					</li>
					<li>
						Parking can be found on and off-campus.
						Please check out
						<a class="underline cursor-pointer" target="_blank" href="https://www.transportation.ucla.edu/campus-parking/visitors">this site</a> for more
						information on on-campus parking.
					</li>
					<li>
						The best way to get to the Palisades Room from The Hill is to walk from Sproul Landing towards BPlate,
						and turn left <strong>before</strong> the stairs going down to BPlate. Don't worry if you've never been before,
						we'll have signs 💗
					</li>
					<li>
						If you’re having trouble finding the venue, contact us at one of the numbers at the end of this page
					</li>
					<li>
						Here are maps of the inside and outside of the venue for reference XOXO
					</li>
				</ul>
			</div>

			<div class="flex-image-layout">
				<img class="pulse-shrink-on-hover" src="/palisades-room-lobby.png" alt="Palisades Room and Lobby" style="border-radius: 40px; padding:20px;"/>
				<img class="pulse-shrink-on-hover" src="/ucla-map.png" alt="Map of UCLA showing the location of the Palisades Room" style="border-radius: 40px; padding:20px;"/>
			</div>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; margin:15px;">
				<ul style="list-style-type:disc;">
					<li>
						Workshops and other events will be happening in Hermosa, which is on the <strong>second floor</strong> of Carnesale Commons.
					</li>
				</ul>
			</div>

			<img class="pulse-shrink-on-hover" src="/malibu-venice-hermosa-rooms.png" alt="Malibu, Venice, and Hermosa Rooms" style="border-radius: 40px; padding:20px;"/>
		</div>
	</section>

	<!-- SECTION 6: GENERAL ADVICE -->
	<section class="max-w-5xl mx-auto" aria-labelledby="general-advice-title">
		<div class="glass-card p-10">
			<h2
				id="general-advice-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				In general...
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif;">
				<p>			
					<strong>Make sure to bring:</strong>
				</p>

				<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; padding:15px;">
					<ul style="list-style-type:disc;">
						<li>
							Your laptop 💻 and a charger ⚡🔌
							<ul style="list-style-type:circle; padding-left:20px;">
								<li>
									Power strips will be readily available on site
								</li>
							</ul>
						</li>
						<li>
							A bag with extra room for your swag (slay)
						</li>
						<li>
							A jacket or hoodie (it can get cold, be prepared!)
						</li>
						<li>
							Snacks! 🧃🥐🍬 We have some scrumptious meals planned (with accommodations for vegetarians)
							but make sure to pack snacks if you’re a picky eater or have specific dietary needs.
						</li>
						<li>
							If you plan to use our sleeping accommodations, don’t forget to bring your own <strong>sleeping essentials</strong>
							(sleeping bag, pillow, blanket).
						</li>
					</ul>
				</div>
				
				<p>			
					<strong>We advise you to:</strong>
				</p>

				<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; padding:15px;">
					<ul style="list-style-type:disc;">
						<li>
							Read our
							<a class="underline cursor-pointer" target="_blank" href="https://docs.google.com/document/d/1I8ujktGRModc_E71z2Q8b6TvxD94Z31PIjcajPnNV7c/edit">code of conduct</a>
							– and follow it!!!
						</li>
						<li>
							Take breaks if you feel tired! 💤
							<ul style="list-style-type:circle; padding-left:20px;">
								<li>
									You’re not required to stay on-site for the full duration of the hackathon 
								</li>
								<li>
									Your well-being is priority #1! Feel free to rest and come back when you’re ready :)
								</li>
							</ul>
						</li>
						<li>
							Eat well, stay hydrated, and walk around every once in a while 
						</li>
						<li>
							Put yourself out there and find new people in our community!!
						</li>
						<li>
							Connect to the WiFi! If you are a UCLA student – use <strong>eduroam</strong> and sign in with
							your UCLA login information. If you are visiting, welcome! You can use <strong>UCLA-WEB</strong>.
						</li>
					</ul>
				</div>

			</div>
		</div>
	</section>

	<!-- SECTION 7: FOR FIRST TIMERS -->
	<section class="max-w-5xl mx-auto" aria-labelledby="first-time-advice-title">
		<div class="glass-card p-10">
			<h2
				id="first-time-advice-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				If this is your FIRST hackathon, 🤯
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif;">
				<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; padding:15px;">
					<ul style="list-style-type:disc;">
						<li>
							Get excited! QWER Hacks is going to be amazing! And even more amazing with you in it!
							No one here will judge you or what you make, so be true to yourself ❗
						</li>
						<li>
							Focus on issues you care about, and what you can do to make the world better! 🌎
						<li>
							Keep your project’s scope/purpose clear and focused, oftentimes simple and concise
							projects are the best ones!
						</li>
					</ul>
				</div>
			</div>
		</div>
	</section>

	<!-- SECTION 8: OTHER QUESTIONS -->
	<section class="max-w-5xl mx-auto" aria-labelledby="other-questions-title">
		<div class="glass-card p-10">
			<h2
				id="other-questions-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				Got other questions?
			</h2>

			<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif;">
				<p>
					If you have any questions, feel free to email us at
					<a
							href="mailto:qwerhacks@gmail.com"
							class="font-semibold underline"
						>
							qwerhacks@gmail.com
					</a>! 
				</p>
				<p>
					You can also call us through these phone numbers:
				</p>
				<div class="space-y-6 text-lg" style="font-family: 'Spectral', serif; padding:15px;">
					<ul style="list-style-type:disc;">
						<li>
							Katie Chung -
							<strong>
								<a
									href="tel:+14083415860"
									class="font-semibold-underline"
								>
									(408) 341-5860
								</a>
							</strong>
						</li>
						<li>
							Max Cabilangan -
							<strong>
								<a
									href="tel:+13105914854"
									class="font-semibold-underline"
								>
									(310) 591-4854
								</a>
							</strong>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</section>

	<!-- SECTION 9: ADDITIONAL UPDATES ANNOUNCEMENT -->
	<section class="max-w-5xl mx-auto" aria-labelledby="additional-updates-title">
		<div class="glass-card p-10">
			<h2
				id="additional-updates-title"
				class="text-3xl md:text-4xl mb-6"
				style="font-family: 'Ranille Normal', serif;"
			>
				Keep your eyes peeled for more details coming soon! 👀👀
			</h2>
	</section>

	<img src="/monocle_dog.png" alt="Monocle Dog (spacer)" class="monocle-dog" />

	<!-- SECTION 10: CTA -->
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

	.flex-image-layout {
		display: flex;
		flex-wrap: wrap;
		flex-direction: row;
	}

	.flex-image-layout img {
		flex: 0 0 50%;
	}

	@-webkit-keyframes pulse-shrink-on-hover {
		to {
			-webkit-transform: scale(0.99);
			transform: scale(0.99);
		}
	}

	@keyframes pulse-shrink-on-hover {
		to {
			-webkit-transform: scale(0.99);
			transform: scale(0.99);
		}
	}

	.pulse-shrink-on-hover {
		display: inline-block;
		vertical-align: middle;
		-webkit-transform: perspective(1px) translateZ(0);
		transform: perspective(1px) translateZ(0);
		box-shadow: 0 0 1px rgba(0, 0, 0, 0);
	}

	.pulse-shrink-on-hover:hover, .pulse-shrink-on-hover:focus, .pulse-shrink-on-hover:active {
		-webkit-animation-name: pulse-shrink-on-hover;
		animation-name: pulse-shrink-on-hover;
		-webkit-animation-duration: 0.3s;
		animation-duration: 0.3s;
		-webkit-animation-timing-function: linear;
		animation-timing-function: linear;
		-webkit-animation-iteration-count: infinite;
		animation-iteration-count: infinite;
		-webkit-animation-direction: alternate;
		animation-direction: alternate;
	}

	@keyframes float-dog {
		0% {
			transform: translateY(0) rotate(0deg);
		}
		100% {
			transform: translateY(-20px) rotate(5deg);
		}
	}

	.astronaut-dog, .monocle-dog {
		opacity: 100%;
		align-self: center;
		height: auto;
		animation: float-dog 6s ease-in-out infinite alternate;
		z-index: 1;
		pointer-events: none;
		display: block;
		margin-left: auto;
		margin-right: auto;
		width: 300px;
	}

</style>
