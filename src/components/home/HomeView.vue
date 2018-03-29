<template>
	
	<div class='home'>
		<mt-header fixed title="孕育宝典 ">
  				<mt-button icon="search" slot="right"></mt-button>
      	</mt-header>
		<div class='container'>
			<ul>
				<router-link tag='li' to='/list/yunqian'>
					<img src="../../assets/img/pic1.png" alt="">
				</router-link>
					
				<router-link tag='li' to='/list/yunzhong'>
					<img src="../../assets/img/pic2.png" alt="">
				</router-link>


				<router-link tag='li' to='/list/chanqian'>
					<img src="../../assets/img/pic3.png" alt="">
				</router-link>
				
				<router-link tag='li' to='/list/chanhou'>
					<img src="../../assets/img/pic4.png" alt="">
				</router-link>
				
				<router-link tag='li' to='/list/chengzhang'>
					<img src="../../assets/img/pic5.png" alt="">
				</router-link>
				
				<router-link tag='li' to='/list/fangzhi'>
					<img src="../../assets/img/pic6.png" alt="">
				</router-link>

			</ul>



		</div>

	</div>

	
</template>

<script>
import { Header } from 'mint-ui';
export default{

}	
</script>
<style scope>
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
	height:auto;
	position: absolute;
	left:0px;
	top:0px;
	background: pink;
	padding-bottom: 40px;
}

.container{
	margin-top:40px;
	/*margin-bottom: 40px;*/
}

.container ul li img{
	width:80%;
	margin-left:auto;
	margin-right:auto;
	display: block;
	padding:10px 0 10px 0;
}
.mint-tabbar > .mint-tab-item.is-selected {
	background: #000000;
	opacity: 0.8;
}
</style>
