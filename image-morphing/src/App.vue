<template>
	<div id="app">
		<Hero />
		<Cards />
	</div>
</template>

<script>
import * as BABYLON from "@babylonjs/core/Legacy/legacy";

import Hero from "./components/hero.vue";
import Cards from "./components/cards.vue";

export default {
	name: "app",
	components: {
		Hero,
		Cards
	},
	mounted() {}
};
</script>

<style lang="scss">
@import "./styles/main";
</style>
