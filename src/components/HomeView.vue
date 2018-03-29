<template>
	
	<div>

		<mt-header fixed title="首页"></mt-header>
			


		    <div class='container'>
		      <ul>
		        <li>

				<router-link to='/list/yunqian'> 

					 <img src="../assets/img/1.jpg" alt="">
	
					</router-link> 
		        </li>

				<li>

<router-link to='/list/yunzhong'>
		          		<img src="../assets/img/2.jpg" alt="">
		        	</router-link>
				 </li>

		       
		      </ul>
		    </div>

	</div>	

</template>
<script>
export default{
	methods:{
	
	}
}	
</script>
<style scope>
ul{
  margin-top:40px;
}
ul li img{
  padding:10px;
  width:188px;
  height:98px;
  margin-left:auto;
  margin-right:auto;
  display: block;
}
</style>


