<template>
	<nav>
		<v-toolbar flat app>
			<v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"><v-icon>menu</v-icon></v-app-bar-nav-icon>
			<v-toolbar-title class="text-uppercase grey--text">
				<span class="font-weight-light">Project</span>
				<span>Management</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn flat color="grey">
				<span>Sign Out</span>
				<v-icon right>exit_to_app</v-icon>
			</v-btn>
		</v-toolbar>

		<v-navigation-drawer  v-model="drawer" class="primary">
			<v-layout column align-center>
				<v-flex class="mt-5">
					<v-avatar size="100">
						<img src="/avatar-1.png" alt="">
					</v-avatar>
					<p class="white--text subheading mt-1">Philippe Mallari</p>
				</v-flex>
				<v-flex class="mt-4 mb-3">
					<Popup />
				</v-flex>
			</v-layout>
			<v-list>
				<v-list-tile v-for="link in links" :key="link.text" router :to="link.route">
					<v-list-tile-action>
						<v-icon class="white--text">{{ link.icon }}</v-icon>
					</v-list-tile-action>
					<v-list-title-content>
						<v-list-tile-title class="white--text">{{ link.text }}</v-list-tile-title>
					</v-list-title-content>
				</v-list-tile>
			</v-list>
		</v-navigation-drawer>

	</nav>
</template>


<script>
	import Popup from './Popup'
	export default {
		components : { Popup },
		data() {
			return {
				drawer: false,
				links: [
					{icon: 'dashboard', text: 'Dashboard', route: '/'},
					{icon : 'folder', text: 'My Projects', route: '/projects'},
					{icon: 'person', text: 'Team', route: '/team'},
				]
			}
		}
	}
</script>