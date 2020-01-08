<template>
  <div class="projects">
    <h1 class="subheading gray--text">Projects</h1>
 
<v-container class="my-5">

	<v-expansion-panel>
		<v-expansion-panel-content v-for="project in myProjects" :key="project.title">
		<div slot="header">{{ project.title }}</div>
			<v-card>
				<v-card-text class="px-4 gray--text">
					<div class="font-weight-bold">{{ project.due }}</div>
					<div>{{ project.content }}</div>
				</v-card-text>
			</v-card>
		</v-expansion-panel-content>
	</v-expansion-panel>

</v-container>

  </div>
</template>

<script>
	export default {
		data() {
			return {
				projects: [
					{title: 'design a new website', person: 'philippe', due: '1st jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'},
					{title: 'design a new website', person: 'philippe', due: '1st jan 2019', status: 'ongoing', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'},
					{title: 'code up the homepage', person: 'ryu', due: '1st jan 2022', status: 'complete', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'}
						,
					{title: 'code up the homepage', person: 'ryu', due: '1st jan 2022', status: 'complete', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'}
						,
					{title: 'code up the homepage', person: 'ryu', due: '1st jan 2022', status: 'complete', content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'}
				]
			}
		},
		computed: {
			myProjects() {
				return this.projects.filter(project => {
					return project.person === 'philippe'
				})
			}
		}
	}
</script>
