<script lang="ts">
	import Arrow from '$lib/media/arrow.svg';
	import { Circle2, Circle } from 'svelte-loading-spinners';

	let text: string = '';

	let error: string | undefined = undefined;

	let success: boolean = false;

	let loading: boolean = false;

	async function submitHandler(e: Event) {
		console.log('Submitted');
		loading = true;
		
		try {
			const resp = await fetch(
				'/api/email?' +
					new URLSearchParams({
						email: text,
					}),
				{
					method: 'POST'
				}
			);

			if (resp.ok) {
				success = true;
				loading = false;
			} else {
				error = await resp.text();
				success = false;
				loading = false;
			}
		} catch (err) {
			let message = 'Unknown Error';
			if (err instanceof Error) message = err.message;
			error = message;
			success = false;
			loading = false;
		}
		console.error(error);
	}
</script>

<form
	class="flex flex-row w-full max-w-[40ch] lg:max-w-[50ch] xl:max-w-[65ch] relative justify-between gap-6 md:gap-8"
	on:submit|preventDefault={submitHandler}
>
	{#if error === undefined && !success}
		<input
			bind:value={text}
			type="email"
			placeholder="Enter your email for updates"
			class="w-full px-5 py-2 leading-tight text-gray-900 bg-white appearance-none font-montserrat_alternates lg:text-2xl xl:text-3xl focus:shadow-outline"
			style="border-radius:50px; box-shadow: 0 8px 20px rgba(0,0,0,0.25), 0 2px 6px rgba(0,0,0,0.15);"
		/>
		{#if !loading}
			<button
				type="submit"
				id="submit"
				class="px-3 py-3 w-[40px] h-[40px] sm:w-[50px] sm:h-[50px]"
				style="border-radius:100%;aspect-ratio:1/1;background:#D4AF37;box-shadow: 0 6px 16px rgba(0,0,0,0.3), 0 2px 6px rgba(0,0,0,0.2);"
			>
				<img src={Arrow} />
			</button>
		{:else}
			<button
				disabled
				type="submit"
				id="submit"
				class="px-2 py-2"
				style="border-radius:100%;aspect-ratio:1/1;width:50px;height:50px;background:#D4AF37;box-shadow: 0 6px 16px rgba(0,0,0,0.3), 0 2px 6px rgba(0,0,0,0.2);"
			>
				<Circle2 size="30" colorOuter="#fff" colorCenter="#fff" colorInner="#fff" />
			</button>
		{/if}
	{:else if success}
		<div>
			<p class="text-center font-montserrat_alternates7 text-white text-xl lg:text-5xl">
				Thank you! Please keep an eye on your email for more info.
			</p>
		</div>
	{:else}
		<div>
			<p class="text-center font-montserrat_alternates7 text-white text-xl lg:text-5xl">
				Error encountered. Please reload and try again.
			</p>
		</div>
		<div class="max-h-[7ch] overflow-scroll">Error: {error}</div>
	{/if}
</form>

<style>
	/* Ensure placeholder uses the same Montserrat font defined in app.postcss
	   Add vendor-prefixed selectors for broad browser support and fallbacks. */
	input::-webkit-input-placeholder { /* Chrome/Opera/Safari */
		text-align: center;
		font-family: 'Montserrat Alternates', sans-serif;
	}
	input::-moz-placeholder { /* Firefox 19+ */
		text-align: center;
		font-family: 'Montserrat Alternates', sans-serif;
	}
	input:-ms-input-placeholder { /* IE 10+ */
		text-align: center;
		font-family: 'Montserrat Alternates', sans-serif;
	}
	input::placeholder { /* Standard */
		text-align: center;
		font-family: 'Montserrat Alternates', sans-serif;
	}
</style>
