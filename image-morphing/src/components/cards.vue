<template>
	<section class="section section--cards">
		<div class="container">
			<div class="row">
				<div class="col-4 card card--1">
					<div class="card__inner">
						<h2>Card 1</h2>
						<canvas id="renderCard1" touch-action="none"></canvas>
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
import { Engine } from "@babylonjs/core/Engines/engine";
import { Scene } from "@babylonjs/core/scene";
import { Vector3 } from "@babylonjs/core/Maths/math";
import { FreeCamera } from "@babylonjs/core/Cameras/freeCamera";
import { HemisphericLight } from "@babylonjs/core/Lights/hemisphericLight";
import { Mesh } from "@babylonjs/core/Meshes/mesh";

export default {
	name: "Cards",
	data() {
		return {};
	},
	mounted() {
		this.runBabylon();
	},
	methods: {
		runBabylon() {
			// Get the canvas element from the DOM.
			const canvas = document.getElementById("renderCard1");

			// Associate a Babylon Engine to it.
			const engine = new BABYLON.Engine(canvas);

			// Create our first scene.
			var scene = new BABYLON.Scene(engine);

			// This creates and positions a free camera (non-mesh)
			var camera = new BABYLON.FreeCamera(
				"camera1",
				new Vector3(0, 5, -10),
				scene
			);

			// This targets the camera to scene origin
			camera.setTarget(Vector3.Zero());

			// This attaches the camera to the canvas
			camera.attachControl(canvas, true);

			// This creates a light, aiming 0,1,0 - to the sky (non-mesh)
			var light = new HemisphericLight(
				"light1",
				new Vector3(0, 1, 0),
				scene
			);

			// Default intensity is 1. Let's dim the light a small amount
			light.intensity = 0.7;

			// Create a grid material
			// var material = new BABYLON.GridMaterial("grid", scene);

			// Our built-in 'sphere' shape. Params: name, subdivs, size, scene
			var sphere = Mesh.CreateSphere("sphere1", 16, 2, scene);

			// Move the sphere upward 1/2 its height
			sphere.position.y = 2;

			// Affect a material
			// sphere.material = material;

			// Our built-in 'ground' shape. Params: name, width, depth, subdivs, scene
			// var ground = Mesh.CreateGround("ground1", 6, 6, 2, scene);

			// Affect a material
			// ground.material = material;

			// Render every frame
			engine.runRenderLoop(() => {
				scene.render();
			});
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
