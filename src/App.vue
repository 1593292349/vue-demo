<template>
	<div>
		{{createVue()}}
	</div>
</template>

<script setup lang="ts">
import Vue,{
	getCurrentScope,
} from 'vue';

window.getCurrentScope=getCurrentScope;

let vm:Vue;
function createVue(){
	console.log('createVue',vm);
	if(!vm){
		vm=new Vue({
			render(h){
				return h('div');
			}
		}).$mount();
	}
}
</script>

<style>

</style>
