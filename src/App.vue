<template>
		<div class="container">
				<div id="nav" class="navbar navbar-start">
						<router-link class="navbar-item" to="/">Todo List</router-link>
						<router-link class="navbar-item" to="/about">About</router-link>
				</div>
				<router-view />
		</div>
</template>

<style>
		#nav.navbar {
				margin-bottom: 5px;
				background: transparent;
		}

		#nav a {
				font-weight: bold;
				color: #2c3e50;
				text-decoration: none;
		}

		#nav a:hover {
				background: transparent;
				color: darkseagreen;
		}


		#nav a.router-link-exact-active {
				color: #42b983;
				background: transparent;
		}
</style>
