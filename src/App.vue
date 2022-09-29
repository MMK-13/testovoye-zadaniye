<template>
	<div class="app">
		<h1 class="app__title">Welcome!</h1>
		<button @click="showPopUp();" class="app__btn">Click me!</button><br><br>
		<PopUp :reveal="revealModal" @toggle="toggle" />
	</div>
</template>

<script>
	import PopUp from './components/PopUp.vue'
	
	export default {
		name: 'App',
		data: () => ({
			revealModal: false
		}),
		components: {
			PopUp
		},
		methods: {
			showPopUp() {
				this.revealModal = !this.revealModal;
			},
			toggle(payload) {
				this.revealModal = payload.reveal;
			}
		}
	}
</script>

<style scoped>
	@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
	@import url('./components/css/App.css');
</style>
