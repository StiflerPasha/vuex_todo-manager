<template>
	<div class="container">
		<h3>Todos</h3>
		<div class="legend">
			<span>Double click to mark as complete</span>
			<span>
				<span class="incomplete-box"></span> = Incomplete
			</span>
			<span>
				<span class="complete-box"></span> = Complete
			</span>
		</div>
		<div class="todos">
			<div v-for="todo in allTodos"
			     :key="todo.id"
			     @dblclick="onDblClick(todo)"
			     class="todo"
			     :class="{'is-complete': todo.completed}">
				{{ todo.title }}
				<i class="fas fa-trash-alt" @click="deleteTodo(todo.id)"></i>
			</div>
		</div>
	</div>
</template>

<script>
  import { mapGetters, mapActions } from 'vuex';
  
  export default {
    name: 'Todos',
    methods: {
      ...mapActions(['fetchTodos', 'deleteTodo', 'updateTodo']),
      onDblClick(todo) {
        const updTodo = {
          id: todo.id,
          title: todo.title,
          completed: !todo.completed,
        };
        this.updateTodo(updTodo);
      },
    },
    computed: {
      ...mapGetters(['allTodos']),
    },
    created() {
      this.fetchTodos();
    },
  };
</script>

<style scoped>
	.container {
		max-width: 80%;
	}
	
	.todos {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-gap: 1rem;
	}
	
	.todo {
		border: 1px solid whitesmoke;
		background: #41b883;
		padding: 1rem;
		border-radius: 5px;
		text-align: center;
		position: relative;
		cursor: pointer;
	}
	
	.is-complete {
		background: #35495e;
		color: whitesmoke;
	}
	
	i {
		position: absolute;
		bottom: 10px;
		right: 10px;
		color: whitesmoke;
		cursor: pointer;
	}
	
	.legend {
		display: flex;
		justify-content: space-around;
		margin-bottom: 1rem;
		font-size: 15px;
	}
	
	.complete-box {
		display: inline-block;
		width: 10px;
		height: 10px;
		background: #35495e;
	}
	
	.incomplete-box {
		display: inline-block;
		width: 10px;
		height: 10px;
		background: #41b883;
	}
	
	@media (max-width: 550px) {
		.todos {
			grid-template-columns: 1fr;
		}
		
		.legend {
			flex-direction: column;
			text-align: center;
		}
	}
</style>
