<template>
	<h1>Добро пожаловать!</h1>
	<button @click="showPopUp();">Click me!</button>
	<PopUp :reveal="revealModal" @toggle="toggle" />
</template>

<script>
	import PopUp from './components/PopUp.vue'

	export default {
		name: 'App',
		data: () => ({
			revealModal: true,
		}),
		components: {
			PopUp
		},
		methods: {
			showPopUp() {
				this.revealModal = true;
			},
			toggle(payload) {
				this.revealModal = payload.reveal;
			}
		}
	}
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
