<template>
	<div>
		首页{{count}}
		<button @click="start">开始</button>
	</div>
</template>

<script setup lang="ts">
import {
	shallowRef,
	watchEffect,
} from 'vue';

console.log('首页')
const count=shallowRef(0);

function start(){
	console.log('start');
	watchEffect(() => {
		console.log(count.value);
	});
	setInterval(() => {
		++count.value;
	},500);
}
</script>

<style>

</style>
