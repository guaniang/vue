<template>
	
	<div class='home'>
		<mt-header fixed :title='str'>
          <router-link to="/" slot="left">
          <mt-button icon="back"></mt-button>
          </router-link>
          <mt-button icon="search" slot="right"></mt-button>
        </mt-header>
		<ul class="container">
			<li v-for='(item,index) in arr'>
				<router-link :to="{ 
					path: '/article', 
					params: { userId: 123 },
					query:{
						names:str,
						idx:index
					}
				}">
				<img :src="require('../../assets/img/tu/'+item.img)" alt="" style="width: 50px; height: 50px;" />
			 	<p>{{item.title}}</p>
				</router-link>
		
			</li>
		</ul>
		
	</div>

</template>
<script>
import '../../mock/mock'
export default{
	data(){
		return {
			arr:[],
			str:""
		}
	},
	mounted(){


		let id = this.$route.params.id;
		this.str = id;
		this.$http({
			method:"get",
			url:'/arList'
		})
			.then(res=>{

				this.arr = res.data[id]['fenlei'];

			})

	}

}
</script>

<style scoped>
*{
	margin: 0;
	padding: 0;
}
html{
	font-size: 18px;
}
ul li{
	padding:10px;
	border-bottom: 1px dashed #000000;
}	
ul li a{
	display: flex;
	flex-direction:row;
	line-height: 50px;
	color: #000000;
	font-size: 14px;
}
ul li a p{
	margin-left: 15px;
}
ul{
	list-style: none;
}
a{
	text-decoration: none;
}
.container{
	margin-top:40px;
	margin-bottom: 40px;
}
</style>