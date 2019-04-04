<template>
	<nav class="navbar" role="navigation" aria-label="main navigation">
		<div class="navbar-brand">
			<router-link class="navbar-item" to="/">
				<h1 class="title is-5">Melvin Hernández</h1>
			</router-link>

			<a @click="burger" role="button" :class="`navbar-burger burger ${navbar.burger}`" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
				<span aria-hidden="true"></span>
				<span aria-hidden="true"></span>
				<span aria-hidden="true"></span>
			</a>
		</div>

		<div id="navbarBasicExample" :class="`navbar-menu ${navbar.menu}`">
			<div class="navbar-start">
				
				<router-link class="navbar-item" to="proyectos">
				Proyectos
				</router-link>

				<div class="navbar-item has-dropdown is-hoverable">
					<a class="navbar-link">
					Certificados
					</a>

					<div class="navbar-dropdown">
						<a class="navbar-item"
						@click.prevent = "showModal('desarrollo-web')"
						>
						Desarrollo Web
						</a>
						<a class="navbar-item"
						@click.prevent = "showModal('vue')"
						>
						Vuejs
						</a>
						<a class="navbar-item"
						@click.prevent = "showModal('laravel')"
						>
						Laravel
						</a>
						<a class="navbar-item"
						@click.prevent = "showModal('git-github')"
						>
						Git-GitHub
						</a>
						<a class="navbar-item"
						@click.prevent = "showModal('js')"
						>
						Javascript
						</a>
						<a class="navbar-item"
						@click.prevent = "showModal('php')"
						>
						PHP
						</a>
						<hr class="navbar-divider">
						<a class="navbar-item"
						@click.prevent = "showModal('carrera-vue')"
						>
						Carrera de Vuejs
						</a>
					</div>
				</div>

				<router-link class="navbar-item"  to="contacto">
				Contacto
				</router-link>
			</div>

			<div class="navbar-end">
				<div class="navbar-item">
					<a href="https://github.com/MelvinH5" target="_blank">
		            	<font-awesome-icon :icon="['fab', 'github']" fixed-width :style="{ color: 'black' }" size="2x"></font-awesome-icon>
		        	</a>
				</div>
				<div class="navbar-item">
					<a href="https://twitter.com/MelvinH05" target="_blank">
		            	<font-awesome-icon :icon="['fab', 'twitter']" fixed-width :style="{ color: '#167df0 ' }" size="2x"></font-awesome-icon>
		        	</a>
				</div>
				<div class="navbar-item">
					<a href="https://www.linkedin.com/in/Melvinh5/" target="_blank">
		            	<font-awesome-icon :icon="['fab', 'linkedin']" fixed-width :style="{ color: '#167df0 ' }" size="2x"></font-awesome-icon>
		        	</a>
				</div>
			</div>
		</div>
	</nav>	
</template>

<script>
	export default {
		data(){
			return {
				navbar: {
					burger: '',
					menu: ''
				}
			}
		},
		methods: {
			burger() {
				if(this.navbar.burger === 'is-active'){
					this.navbar.burger = '';
					this.navbar.menu = '';
				}
				else{
					this.navbar.burger = 'is-active';
					this.navbar.menu = 'is-active';
				}
			},
			showModal(certificado) {
				switch(certificado) {
					case 'php': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/php.png">
								</p>
								`);
						break;
					case 'js': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/js.png">
								</p>
								`);
						break;
					case 'vue': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/vue-profesional.png">
								</p>
								`);
						break;
					case 'laravel': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/laravel.png">
								</p>
								`);
						break;
					case 'git-github': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/git-github.png">
								</p>
								`);
						break;
					case 'carrera-vue': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/carrera-vue.png">
								</p>
								`);
						break;
					case 'desarrollo-web': 
							this.$modal.open(`
								<p class="image">
									<img src="../assets/certificados/desarrollo-web.png">
								</p>
								`);
						break;
				}
			}
		}
	}
</script>

<style scoped>
	.title:hover {
		color: #7957d5;
	}
</style>

