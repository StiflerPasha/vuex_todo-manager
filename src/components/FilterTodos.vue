<template>
	<div class="container">
		<div class="field is-horizontal">
			<div class="field-label is-normal">
				<label class="label">Filter Todos:</label>
			</div>
			<div class="field-body">
				<div class="field is-narrow">
					<div class="control">
						<div class="select is-fullwidth is-info">
							<select @change="filterTodos($event)">
								<option value="5">5</option>
								<option value="10">10</option>
								<option value="20">20</option>
								<option value="50">50</option>
								<option value="100">100</option>
								<option value="200">200</option>
							</select>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
  import { mapActions } from 'vuex';
  
  export default {
    name: 'FilterTodos',
    methods: {
      ...mapActions(['filterTodos']),
    },
  };
</script>

<style scoped>
	.container {
		margin: 15px 0;
	}
</style>
