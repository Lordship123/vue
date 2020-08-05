<template>
	<form @submit.prevent="onsubmit">  <!-- привент не перезагружает форма -->
	<input type="text" v-model="title">
	<button>Создать</button>

	</form>


</template>

<script>
	
export default{
	data(){
		return{
			title: ''
		}
	},
	methods:{
		onsubmit(){
			if (this.title.trim()) {
				const newTodo ={
					id: this.id,
					title: this.title,
					completed: false
				}
				this.$emit('add-todo', newTodo)
				this.title = ''

			}

		}
	}
}

</script>