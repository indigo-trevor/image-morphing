<template>
	<section class="section section--cards">
		<div class="container">
			<div class="row">
				<div class="col-4 card card--1">
					<div class="card__inner">
						<h2>Card 1</h2>
					</div>
				</div>
				<div class="col-4 card card--2">
					<div class="card__inner">
						<h2>Card 2</h2>
					</div>
				</div>
				<div class="col-4 card card--3">
					<div class="card__inner">
						<h2>Card 3</h2>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: "Cards",
	data() {
		return {};
	},
	computed: {},
	created() {
		this.sayHello();
	},
	methods: {
		sayHello() {
			console.log("Say hello");
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
