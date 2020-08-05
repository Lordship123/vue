<template>
	<li>
		<span v-bind:class="{done: todo.completed}">
			<input type="checkbox" v-on:change="todo.completed = !todo.completed">
			<strong>{{ index + 1 }}</strong>
			{{ todo.title }}

		</span>
		<button v-on:click="$emit('remove-todo', todo.id )">Удалить</button>
	</li>


</template>

<script>
	
export default{
	props: {
		todo: {
			type: Object,
			required: true

		},
		index: Number
	}
}

</script>

<style>
	li{
	list-style: none;
	display: flex;
	justify-content: space-between;
	margin: 0;
	padding: 0;
	}

.done{
	text-decoration: line-through;

}
</style>