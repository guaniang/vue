<template>
  <div>
     <mt-tabbar v-model="selected" fixed>
	  <mt-tab-item id="首页">
	  <router-link to='/home'>
	    	首页<br>home
		</router-link>
	  </mt-tab-item>
	  
	  <mt-tab-item id="收藏">
	    <router-link to='/fav'>
	    	收藏<br>fav
		</router-link>
	    
	  </mt-tab-item>
	  <mt-tab-item id="历史记录">
	   
	   	<router-link to='/history'>
	    	历史记录<br>history
		</router-link>

	  </mt-tab-item>
	  <mt-tab-item id="设置">
	 	
	 	<router-link to='/config'>
	    	设置<br>config
		</router-link>
	   
	   </mt-tab-item>
	 </mt-tabbar>
    
  </div>
</template>

<script>
import { Tabbar, TabItem } from 'mint-ui';
export default {
  data(){
  	return{
  		selected:""
  	}
  }
}
</script>
<style scoped>

.mint-tabbar a{
	color: #FFFFFF;
	text-align: center;
	line-height: 20px;
	background: #000000;
	font-size: 14px;
}
.mint-tabbar > .mint-tab-item.is-selected {
	background: #000000;
	opacity: 0.8;
}
</style>