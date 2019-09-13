<template>
		<div>
				<div id="nav">
						<router-link to="/">Todo List</router-link>
						|
						<router-link to="/about">About</router-link>
				</div>
				<router-view />
		</div>
</template>

<style>
		body {
				font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
				line-height: 1.6;
				background: #e8f7f0;
		}

		#nav {
				padding: 5px;
		}

		#nav a {
				font-weight: bold;
				color: #2c3e50;
				text-decoration: none;
		}

		#nav a.router-link-exact-active {
				color: #42b983;
		}
</style>
