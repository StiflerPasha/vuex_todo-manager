<template>
		<div class="container">
				<AddTodo />
				<FilterTodos />
				<Todos />
		</div>
</template>

<script>
   import Todos       from '../components/Todos';
   import AddTodo     from '../components/AddTodo';
   import FilterTodos from '../components/FilterTodos';

   export default {
	  name: 'home',
	  components: {
		 FilterTodos,
		 Todos,
		 AddTodo,
	  },
   };
</script>

<style scoped>
		.container {
				max-width: 1100px;
				margin: auto;
				overflow: auto;
				padding: 0 2rem;
		}
</style>
