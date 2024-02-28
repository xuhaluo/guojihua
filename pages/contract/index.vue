<template>
	<view class="content">
		<home-money-list @loadingStatus="loadingStatus" ref="homeList" />
	</view>
</template>

<script>
	import homeMoneyList from '@/components/home-money-list.vue';
	var itemType = require("@/common/p/base-data.js").itemType;
	export default {
		components:{
			homeMoneyList
		},
		
		data() {
			return {
				itemType:itemType,
			}
		},
		
		onLoad() {
			
			// console.log("itemType: " + JSON.stringify(itemType));
		},
		methods: {
			publish(item){
				console.log("item: " + JSON.stringify(item));
			},
			loadingStatus(e){
				this.status = e;
			},
			
		}
	}
</script>

<style>
.content {
	text-align: center;
	padding-top: 0px;
	padding-bottom: 56px;
	height: 200px;
}

.grid-item-wrap{
	margin-top: 15px;
	border-color: #E5E5E5;
	border-width: 1px;
	border-style: solid;
	width: 100%;
}	

.grid-item-left , .grid-item-right{
	margin-top: 0px;
	border-width: 1px;
	border-bottom-width: 0;
	border-right-width: 0;
	border-style: solid;
	padding: 25px 0;
	border-color: #E5E5E5;
	border-radius: 0px;
	font-size: 15px;
	width: 50%;
}
.grid-item-left {
	border-left-width: 0;
}
.grid-item-wrap:nth-child(-n+2){
	border-top-width: 0;
}
</style>
