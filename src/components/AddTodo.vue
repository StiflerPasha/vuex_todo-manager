<template>
		<div class="container">
				<form @submit="onSubmit">
						<div class="field has-addons">
								<p class="control is-expanded">
										<input class="input is-rounded" type="text" v-model="title" placeholder="Add Todo...">
								</p>
								<p class="control">
										<a class="button is-primary is-rounded">
												<span class="icon is-small">
														<i class="fas fa-check"></i>
												</span>
												<span>Save</span>
										</a>
								</p>
						</div>
				</form>
		</div>
</template>

<script>
   import { mapActions } from 'vuex';

   export default {
	  name: 'AddTodo',
	  data() {
		 return {
			title: '',
		 };
	  },
	  methods: {
		 ...mapActions(['addTodo']),
		 onSubmit(e) {
			e.preventDefault();
			this.title.trim() && this.addTodo(this.title);
			this.title = '';
		 },
	  },
   };
</script>

<style lang="scss" scoped>
</style>
