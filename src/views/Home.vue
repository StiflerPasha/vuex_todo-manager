<template>
		<div>
				<AddTodo />
				<FilterTodos />
				<Todos />
		</div>
</template>

<script>
   import AddTodo     from '../components/AddTodo';
   import FilterTodos from '../components/FilterTodos';
   import Todos       from '../components/Todos';

   export default {
	  name: 'home',
	  components: {
	   AddTodo,
	   FilterTodos,
	   Todos,
	  },
   };
</script>

<style lang="scss" scoped>
		.container {
				max-width: 1100px;
				padding: 0 2rem;
		}
</style>
