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
					<label for="email" class="card__subscribing-email">
						Email-adress
						<span :class="classes">{{ emailExist.text }}</span>
					</label>
					<input id="email" type="email" class="card__subscribing-input" v-model="email">
					<button class="card__subscribing-button" @click="subscribe()">Subscribe!</button>
				</div>
				<div class="card__privacy">
					<input id="privacy" type="checkbox" class="card__privacy-input">
					<label for="privacy" class="card__privacy-label">I'm agree with privacy policy</label>
				</div>
			</div>
			<div class="card__right">
				<div class="card__images">
					<img src="@/assets/bg-img.png" class="card__image" />
					<img src="@/assets/rectangle.png" class="card__backimage back-image-1" />
					<img src="@/assets/rectangle.png" class="card__backimage back-image-2" />
				</div>
				<button class="card__close" @click="hide();">X</button>
			</div>
		</div>
	</div>
</template>


<script type="text/javascript">
	export default {
		name: 'PopUp',
		data: () => ({
			email: '',
			emails: [],
			emailExist: {
				text: '',
				type: ''
			}
		}),
		props: ['reveal'],
		methods: {
			hide() {
				this.$emit('toggle', {
					reveal: !this.$props.reveal,
				});
			},
			subscribe() {
				let e = this.emails.find((em) => em === this.email)
				if (e === undefined) {
					this.emails.push(this.email)
					this.email = ''
					this.emailExist.type = 'success'
					this.emailExist.text = 'You have successfully subscribed to the newsletter'
				} else {
					this.emailExist.type = 'danger'
					this.emailExist.text = 'You have already subscribed to the newsletter'
				}
				console.log(e)
			}
		},
		computed: {
			classes() {
				return this.emailExist.type
			}
		}
	}
</script>


<style type="text/css" scoped>
	@import url('./css/PopUp.css');
	@import url('./css/PopMessage.css');
</style>