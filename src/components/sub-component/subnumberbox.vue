<template>
    <div class="mui-numbox" data-numbox-min='1'>
		<button class="mui-btn mui-btn-numbox-minus" type="button">-</button>
			<input id="test" class="mui-input-numbox" type="number" :value="value" @change="getinputnum()" ref="inputnum"/>
		<button class="mui-btn mui-btn-numbox-plus" type="button">+</button>
	</div>
</template>
<script>
import mui from "../../lib/MUI/js/mui.min.js"
export default {
    data(){
        return {
            selectCount:1,
        }
    },
    props:[
        'max',
        'value',
        'id'
    ],
    watch:{
        max:function(newval,oldval){
            mui('.mui-numbox').numbox().setOption('max',this.max)
        },
    },
    methods:{
        getinputnum(){
            this.selectCount=this.$refs.inputnum.value;
            this.$emit('getcount',this.selectCount);
            this.$emit('getshopcarid',this.id);
        },
    }
}
</script>
<style lang="scss" scoped>

</style>