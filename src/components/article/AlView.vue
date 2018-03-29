<template>
	
	<div class='ar'>
		<mt-header  :title="qqurl">
		    <mt-button icon="back" slot="left" @click="fn"></mt-button>
		  
		  <mt-button to="/fav" slot="right">
		  	<img @click="f1"  style="width: 25px; height: 25px;" src="../../assets/img/xsc.png"/>
		  </mt-button>
		  
		</mt-header>
     <div class="center">
     	{{content}}
     </div>
		
		
	</div>

</template>

<script>
export default{
	data(){
		return {
			content:"",
			names:"",
			qqurl:""
		}
	},
	methods:{
		fn(){
			this.$router.history.go(-1)
		},
		f1(){
			var ls = localStorage;
			var num=''
			if(!ls.getItem("f")){
				var arr =ls.setItem('f',"[]")
			}
			var brr=JSON.parse(ls.getItem('f'))
			if (brr.includes(this.qqurl)) {
				alert('已收藏')
			}else{
				brr.push(this.qqurl)
				alert('收藏成功')
			}
			brr.forEach(item => {
				num += item
			});
			var jsondata=JSON.stringify(brr)
			ls.setItem('f',jsondata)
		}
	},
	mounted(){
		let names = this.$route.query.names;
		let idx = this.$route.query.idx;

		this.$http({
			method:"get",
			url:'/arList'
		})
			.then(res=>{
				this.content = res.data[names]['fenlei'][idx].content
				this.qqurl=res.data[names]['fenlei'][idx].title
			})

	}

}	
</script>
<style>
html{
	font-size: 18px;
}
ul{
	list-style: none;
}
a{
	text-decoration: none;
}
.ar{
	width:100%;
	height:100%;
	position: absolute;
	left:0px;
	top:0px;
}
.center{
	padding: 15px;
}
</style>

