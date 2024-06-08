<script lang="ts">
	import { page } from '$app/stores';

	$: path = $page.url.pathname;
</script>

<div class="main">
	<section>
		<header>
			<h1>Crypto-V</h1>
		</header>
		<nav>
			<a class={path === '/dashboard' ? 'active' : ''} href="/dashboard">
				<img src="/dashboard.svg" alt="dashboard icon" />
				Dashboard
			</a>
			<a class={path === '/market' ? 'active' : ''} href="/market">
				<img src="/market.svg" alt="market icon" />

				Market</a
			>
		</nav>
	</section>
	<slot></slot>
</div>

<style>
	.main {
		display: flex;
	}

	nav {
		display: flex;
		flex-direction: column;
		row-gap: 16px;
	}

	a {
		display: flex;
		align-items: center;
		column-gap: 18px;
		width: 176px;
		height: 46px;
		color: #828282;
		text-decoration: none;
		padding: 12px 28px;
		border-radius: 10px;
		font-size: 16px;
		transition: 0.3s linear;

		&.active {
			background-color: #0096ff;
			color: white;
		}
	}
</style>
