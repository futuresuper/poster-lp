<script>
	import Logo from '../lib/Logo.svelte';

	let number = '$82,262';

	const ageToDollars = {
		'At 20': 8766,
		'At 25': 26046,
		'At 30': 52000,
		'At 35': 82262,
		'At 40': 116782,
		'At 45': 154917,
		'At 50': 200598,
		'At 55': 259209,
		'At 60': 311504,
		'At 65': 348795,
		'At 70': 428923
	};

	const ages = [
		'At 20',
		'At 25',
		'At 30',
		'At 35',
		'At 40',
		'At 45',
		'At 50',
		'At 55',
		'At 60',
		'At 65',
		'At 70'
	];

	function handleChange(event) {
		number = '$' + ageToDollars[event.target.value].toLocaleString();
	}
</script>

<header>
	<div class="container">
		<Logo colour="white" />
		<h1>
			If you don’t know exactly what your superannuation fund invests in, your future savings could
			be contributing directly and significantly to the climate&nbsp;crisis.
		</h1>
	</div>
</header>

<main>
	<div class="container">
		<div class="how-it-works">
			<p>Here’s how it works</p>
			<svg
				width="25"
				height="30"
				viewBox="0 0 25 30"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M12.8281 0.324463C12.0156 0.324463 11.4375 0.886963 11.4375 1.69946V22.2776L11.5625 25.6213L6.875 20.4807L3.3125 16.9807C3.07812 16.7307 2.70312 16.6057 2.32812 16.6057C1.54688 16.6057 0.984375 17.1995 0.984375 17.9651C0.984375 18.3401 1.125 18.6682 1.42188 18.9807L11.7812 29.3713C12.0781 29.6838 12.4375 29.8401 12.8281 29.8401C13.2188 29.8401 13.5781 29.6838 13.875 29.3713L24.25 18.9807C24.5469 18.6682 24.6719 18.3401 24.6719 17.9651C24.6719 17.1995 24.1094 16.6057 23.3281 16.6057C22.9531 16.6057 22.5938 16.7307 22.3438 16.9807L18.7812 20.4807L14.1094 25.6057L14.2188 22.2776V1.69946C14.2188 0.886963 13.6406 0.324463 12.8281 0.324463Z"
					fill="white"
				/>
			</svg>
		</div>

		<div class="main-text">
			<p>
				If you work or live in Australia, superannuation is compulsory. You probably already
				know&nbsp;that.
			</p>
			<p>
				You may have chosen your super fund yourself. You might have just stuck with the one given
				to you when you got your first job flipping burgers at 15. Your super might even be
				scattered across several different accounts (that’s a whole separate&nbsp;conversation).
			</p>
			<p>
				Whoever you’re with, they invest your money until you’re ready to access
				it&nbsp;at&nbsp;retirement.
			</p>
			<p>
				<select on:change={handleChange} on:blur={handleChange}>
					{#each ages as age}
						{#if age === 'At 35'}
							<option value={age} selected>{age}</option>
						{:else}
							<option value={age}>{age}</option>
						{/if}
					{/each}
				</select>
				the average Australian has
				<span id="number">{number}<sup>^</sup></span> in superannuation. That’s a lot of money potentially
				being invested into fossil fuels on your behalf, doing irreparable damage to&nbsp;the&nbsp; environment.
			</p>
			<p>
				It takes five minutes to move your super to a fund that doesn’t invest your money into
				fossil fuels. Invest for the&nbsp;future&nbsp;today.
			</p>
			<div style="text-align: center">
				<button href="https://www.futuresuper.com.au/?utm_source=poster-lp">
					Make the switch
				</button>
			</div>
		</div>
	</div>
</main>

<footer>
	<div class="container footer">
		<Logo colour="black" />
		<div>
			<p>
				^ Data from Association of Superannuation Funds of Australia, Experience to date with the
				early release of superannuation, June 2020, pg. 15. The final number was reached by
				determining the average of the female and male super balance.
			</p>
			<p>
				We acknowledge the Traditional Custodians of the lands on which we operate. We pay our
				respects to their Elders, past, present and emerging, and recognise that sovereignty was
				never ceded. See our Reconciliation Action Plan.
			</p>
			<p>
				All information provided is general in nature only. We recommend you seek financial advice
				when considering if Future Super is right for your objectives and needs. When considering
				returns, past performance is not indicative of future performance.
			</p>
			<p>
				<a href="https://www.futuresuper.com.au/fund-information/">Fund Information</a
				>&nbsp;&nbsp;•&nbsp;&nbsp;<a href="https://www.futuresuper.com.au/terms-and-conditions/"
					>Terms & Conditions</a
				>&nbsp;&nbsp;•&nbsp;&nbsp;<a href="https://www.futuresuper.com.au/privacy-policy/"
					>Privacy Policy</a
				>
			</p>
		</div>
	</div>
</footer>

<style>
	header,
	main,
	footer {
		padding: 40px;
		display: flex;
		justify-content: center;
	}

	header {
		background: black;
		color: white;
	}

	h1 {
		font-family: 'HelveticaNeueLTPro-Md';
		font-size: 60px;
		margin-top: 110px;
		margin-bottom: 60px;
		line-height: 130%;
	}

	.main-text {
		margin-top: 80px;
	}

	p {
		font-size: 30px;
		line-height: 130%;
		margin-bottom: 40px;
	}

	.container {
		max-width: 1200px;
	}

	select {
		outline: none;
		border: 1px solid black;
		border-radius: 0;
		font-size: inherit;
		padding: 2px 8px;
	}

	#number {
		border: 1px solid black;
		padding: 8px 8px 0px 8px;
	}

	.how-it-works {
		background: black;
		border: 1px solid white;
		position: absolute;
		margin-top: -74px;
		padding: 16px 26px;
		display: inline-flex;
		align-items: center;
		justify-content: center;
	}

	.how-it-works > p {
		color: white;
		font-size: 22px;
		margin: 0;
		padding-top: 4px;
	}

	.how-it-works > svg {
		margin-left: 20px;
	}

	button {
		background: black;
		color: white;
		font-size: 50px;
		border: 0;
		padding: 12px 60px;
		margin: 20px 0 80px 0;
	}

	footer {
		border-top: 1px solid black;
	}

	.footer {
		display: grid;
		grid-template-columns: 50% 50%;
		margin: 40px 0;
	}

	.footer > div > p {
		margin: 0 0 26px 0;
		font-size: 18px;
	}

	a {
		color: black;
	}

	sup {
		font-size: 16px;
	}

	@media (max-width: 900px) {
		h1 {
			font-size: 46px;
		}
	}

	@media (max-width: 600px) {
		header,
		main,
		footer {
			padding: 20px;
		}

		h1 {
			font-size: 30px;
		}

		p {
			font-size: 18px;
		}

		.how-it-works {
			margin-top: -54px;
		}

		.how-it-works > p {
			font-size: 16px;
		}

		button {
			font-size: 30px;
			width: 100%;
			padding: 12px;
		}

		.footer {
			grid-template-columns: 100%;
			row-gap: 20px;
		}

		.footer > div > p {
			font-size: 12px;
		}

		sup {
			font-size: 12px;
		}
	}
</style>
