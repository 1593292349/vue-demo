<template>
	<div>
		{{createVue()}}
		<button @click="++count">render</button>
		{{count}}
	</div>
</template>

<script setup lang="ts">
import Vue,{
	shallowRef,
	getCurrentScope,
} from 'vue';

window.getCurrentScope=getCurrentScope;

const count=shallowRef(1);
let vm:Vue;
function createVue(){
	console.log('createVue',vm);
	if(!vm){
		vm=new Vue({
			render(h){
				return h('div');
			}
		}).$mount();
	}else{
		vm.$forceUpdate();
	}
}
</script>

<style>

</style>
