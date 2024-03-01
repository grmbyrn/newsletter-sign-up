<script lang="ts">
	let email: string = '';
	let buttonPressed: boolean = false;

	const handleSubscribe = () => {
		buttonPressed = !buttonPressed;
	};
</script>

<div class="container">
	{#if !buttonPressed}
		<img src="./assets/images/illustration-sign-up-mobile.svg" class="img" alt="sign up" />
		<div class="inner-container">
			<h1 class="heading">Stay updated!</h1>
			<p class="para">Join 60,000+ product managers receiving monthly updates on:</p>
			<ul class="list">
				<div class="list-item">
					<img src="./assets/images/icon-list.svg" alt="list" />
					<li>Product discovery and building what matters</li>
				</div>
				<div class="list-item">
					<img src="./assets/images/icon-list.svg" alt="list" />
					<li>Measuring to ensure updates are a success</li>
				</div>
				<div class="list-item">
					<img src="./assets/images/icon-list.svg" alt="list" />
					<li>And much more!</li>
				</div>
			</ul>

			<div class="email">
				<p>Email address</p>
				<input bind:value={email} type="text" placeholder="email@company.com " />
				<button on:click={handleSubscribe}>Subscribe to monthly newsletter </button>
			</div>
		</div>
	{:else}
		<div class="confirmation">
			<img src="./assets/images/icon-success.svg" alt="success" />
			<h1>Thanks for subscribing!</h1>
			<p>
				A confirmation email has been sent to <span>ash@loremcompany.com</span>. Please open it and
				click the button inside to confirm your subscription.
			</p>
		</div>
		<div class="confirmation-btn">
			<button on:click={handleSubscribe}> Dismiss message </button>
		</div>
	{/if}
</div>
<div class="attribution">
	Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
		>Frontend Mentor</a
	>. Coded by <a href="https://github.com/grmbyrn">grmbyrn</a>.
</div>

<style>
	.container {
		width: 23.438rem;
		background-color: #ffffff;
		display: block;
		margin-left: auto;
		margin-right: auto;
	}

	.inner-container {
		padding: 0px 24px 40px;
	}

	.img {
		position: relative;
		top: -20px;
	}

	.heading {
		font-weight: bold;
		color: #242742;
		font-size: 40px;
	}

	.para {
		color: #242742;
		font-size: 16px;
	}

	.list {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		padding: 0px;
		margin: 0px;
		margin-top: 24px;
	}

	.list-item {
		display: flex;
		gap: 16px;
	}

	.list-item li {
		list-style: none;
		font-size: 16px;
		color: #242742;
	}

	.email {
		margin-top: 40px;
	}

	.email p {
		font-size: 12px;
		font-weight: bold;
	}

	.email input {
		width: 100%;
		padding: 16px 24px;
		border-radius: 8px;
		border: 1px solid #d8d8d8;
		margin-top: 8px;
	}

	.email button,
	.confirmation-btn button {
		margin-top: 24px;
		width: 100%;
		background-color: #242742;
		border: none;
		color: #ffffff;
		border-radius: 8px;
		padding: 18px 46px 14px 48px;
		cursor: pointer;
	}

	.email button:hover,
	.confirmation-btn button:hover {
		background-image: linear-gradient(#ff6a3a, #ff527b);
	}

	.confirmation {
		padding: 149px 24px;
		color: #242742;
	}

	.confirmation h1 {
		font-size: 40px;
	}

	.confirmation p {
		font-size: 16px;
	}

	.confirmation p span {
		font-weight: bold;
	}

	.confirmation-btn {
		margin-top: 149px;
		padding: 0px 24px;
		padding-bottom: 40px;
	}

	.confirmation-btn button {
		width: 100%;
	}

	.attribution {
		font-size: 11px;
		text-align: center;
	}
	.attribution a {
		color: hsl(228, 45%, 44%);
	}
</style>
