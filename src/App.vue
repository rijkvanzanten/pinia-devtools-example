<template>
	<p>
		Counter: {{ count }}
		<button @click="increment">+</button>
	</p>
</template>

<script>
import { defineComponent, toRefs } from "vue";
import { useCounterStore } from "./stores/counter";

export default defineComponent({
	setup() {
		const counter = useCounterStore();

		const { count } = toRefs(counter);

		return { count, increment };

		function increment() {
			counter.count++;
		}
	},
});
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
