<template>
	<div class='home'>
	<mt-header title="收藏 ">
  				<mt-button icon="search" slot="right"></mt-button>
      	</mt-header>
      <div class="main">
      	<ul>
      		<li v-for="item in arr" @click="fn">
      			{{item}}
      		</li>
      	</ul>
      </div>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				val:'',
				arr:[]
			}
		},
		methods:{
		fn(){
//						/#/article?names=yunqian&idx=0
			this.$router.push('/article?names=yunqian&idx=0')
		}
	},
		mounted(){
			var ls=localStorage;
			var str=''
			var val=ls.getItem("f")
			var arr=JSON.parse(val)
			arr.forEach(item =>{
				str+='a'+item
			});
			var brr=str.split('a')
			this.arr=brr
		}
	}
</script>
<style scoped>
*{
	margin: 0;
	padding: 0;
}
ul{
	list-style: none;
}
a{
	text-decoration: none;
}
.home{
	width:100%;
	height:100%;
	position: absolute;
	left:0px;
	top:0px;
}
.main{
	padding: 25px;
	color: #000000;
}
</style>