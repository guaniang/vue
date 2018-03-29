<template>
	
	<div>

		<!-- <mt-header fixed title="列表"></mt-header> -->
		
		<ul>
			<li v-for='item in brr'>

				{{item.title}}
					
			</li>
		</ul>

	</div>	

</template>
<script>
import '../mock/mock'
export default{

	data(){
		return {
			brr:[]
		}
	},
	mounted(){	

		let id = this.$route.params.id;

		this.$http({
			url:"/list",
			method:"get"
		})
			.then(res=>{
					
				let arr = res.data[id]['fenlei'];

				this.brr = arr;


			})
	}
}	
</script>
<style scoped>

.home{
	width:100%;
	height:100%;
	position: absolute;
	left:0px;
	top:0px;
}

</style>




