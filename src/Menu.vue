<template>
  <div class="menu">
		<div class="bind">
			<h1>SPA</h1>
			<div class="list" @click="toggle"/>
		</div>
		
		<transition name="fade">
			<div class="link" v-show="popout">
				<router-link to="/about">About</router-link>
				<router-link to="/courses">Courses</router-link>
				<router-link to="/booking">Booking</router-link>
			</div>
		</transition>

  </div>
</template>

<script>
	export default {
		data(){
			return {
				popout: false,
				screen: '',
			};
		},
		mounted(){
			this.$nextTick(function(){
				this.screen = window.innerWidth;
				if(this.screen > 700){
					this.popout = true;
				}
			});
			const that = this;
			window.onresize = function(){
				that.screen = window.innerWidth;
			};
		},
		methods: {
			toggle(){
				return this.popout = !this.popout;
			},
		},
		watch: {
			screen(val){
				if(val > 700){
					return this.popout = true;
				}
			},
		},
	};
</script>

<style scoped>
h1{
	font-size: 2rem;
	font-family: monospace, Arial;
	color: #42b983;
}
.menu{
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 0 80px;
	background-color: #fff;
	line-height: 2rem;
	height: 80px;
}
.list{
	display: none;
}
a{
	display: inline-block;
	text-decoration: none;
	font-size: 1rem;
	padding: 0 2rem;
	color: #42b983;
	line-height: 80px;
	box-sizing: border-box;
}
a:hover{
	background-color: #42b983;
	color: #fff;
}
a.router-link-active{
	text-shadow: 1px 1px 2px #42b983;
}

@media(max-width: 700px){
	.list{
		display: block;
		background-image: url(./img/list.png);
		height: 40px;
		width: 40px;
		background-position: center center;
		background-size: cover;
		box-sizing: border-box;
		cursor: pointer;
		opacity: 0.5;
	}
	.menu{
		display: block;
		padding: 0;
	}
	.bind{
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 20px;
	}
	.link{
		position: absolute;
		top: 80px;
		right: 0;
	}
	a{
		display: block;
		text-align: center;
		line-height: 90px;
		background-color: #fff;
		opacity: 0.9;
	}
	.fade-leave { opacity: 1; }
	.fade-leave-active { transition: opacity .5s }
	.fade-leave-to { opacity: 0; }
	.fade-enter { opacity: 0; }
	.fade-enter-active  { transition: opacity .5s }
	.fade-enter-to { opacity: 1; }
}
</style>
