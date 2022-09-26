<template>
	<div class="popup" v-show="reveal">
		<div class="overlay" @click="hide();"></div>
		<div class="card">
			<div class="card__left">
				<div class="card__title">
					10%<span>off</span>
				</div>
				<div class="card__subtitle">
					your first order
				</div>
				<div class="separator"></div>
				<div class="card__text">
					Subscrive to recieve 10% off promocode plus exclusive offers and deals
				</div>
				<div class="card__subscribing">
					<label for="email" class="card__subscribing-email">Email-adress</label>
					<input id="email" type="email" class="card__subscribing-input">
					<button class="card__subscribing-button">Subscribe!</button>
				</div>
				<div class="card__privacy">
					<input id="privacy" type="checkbox" class="card__privacy-input">
					<label for="privacy" class="card__privacy-label">I'm agree with privacy policy</label>
				</div>
			</div>
		</div>
	</div>
</template>


<script type="text/javascript">
	export default {
		name: 'PopUp',
		props: [
		'reveal'
		],
		methods: {
			hide() {
				this.$emit('toggle', {
					reveal: !this.$props.reveal
				})
			}
		}
	}
</script>


<style type="text/css">
	@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
	@import url('./css/PopUp.css');
	.popup {
		text-align: left;
		font-family: 'Roboto', sans-serif;
		position: fixed;
		display: flex;
		justify-content: center;
		align-items: center;
		top: 0;
		border: 0;
		left: 0;
		right: 0;
	}
	.overlay {
		position: fixed;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		background-color: rgba(0, 0, 0, 0.75);
	}
	.card {
		width: 864px;
		background-color: #FFF;
		color: #333;
		padding: 40px 32px;
		position: fixed;
		top: 50px;
		border-radius: 8px;
		box-shadow: 0px 8px 20px 0px #444B4D26;
	}.card__btn {
		position: absolute;
		top: 10px;
		right: 10px;
		display: inline-block;
		border: 1px solid #red;
		border-radius: 4px;
		background-color: rgb(255, 25, 25);
		color: #fff;
		padding: 6px 8px;
		font-weight: 400;
		font-size: 16px;
		cursor: pointer;
	}
	/* Beginning */
	.card__title {
		font-weight: 700;
		font-size: 104px;
		line-height: 104px;
	}
	.card__title span {
		font-size: 24px;
		color: #2F3639;;
	}
	.card__subtitle {
		font-weight: 700;
		font-size: 24px;
		line-height: 100%;
		margin-top: 16px;
		color: #828688;
	}
	.card__left {
		width: 416px;
	}
	.separator {
		width: 67px;
		height: 2px;
		background: #C24DFE;
		border-radius: 10px;
		margin: 26px 0;
	}
	.card__text {
		font-weight: 400;
		font-size: 14px;
		line-height: 120%;
		color: #595E61;
		width: 373px;
		margin-bottom: 40px;
	}
	.card__subscribing {
		display: flex;
		flex-direction: column;
	}
	.card__subscribing-email {
		font-weight: 700;
		font-size: 12px;
		line-height: 14px;
		color: #828688;
		margin-bottom: 8px;
	}
	.card__subscribing-input {
		height: 20px;
		width: 302px;
		border: 1px solid #D5D7D7;
		border-radius: 6px;
		padding: 10px 16px;
		margin-bottom: 16px;
	}
	.card__subscribing-input:focus, .card__subscribing-input:hover {
		outline: #C24DFE;
		border: 1px solid #C24DFE;;
	}
	.card__subscribing-button {
		width: 106px;
		height: 40px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 13px 24px;
		gap: 10px;
		background: #C24DFE;
		border-radius: 35px;
		font-weight: 700;
		font-size: 12px;
		line-height: 14px;
		color: #FFF;
		border: none;
		margin-bottom: 16px;
	}
	.card__privacy {
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.card__privacy-label {
		font-weight: 500;
		font-size: 14px;
		line-height: 16px;
		color: #595E61;
		margin-left: 12px;
	}
</style>