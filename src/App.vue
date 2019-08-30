<template>
    <div>
        <mt-header fixed title="标题"></mt-header>
        <mt-button type="default" size="small">按钮</mt-button>
        <mt-button type="primary" size="large">按钮</mt-button>
        <mt-button type="danger" size="normal" @click="show()">按钮</mt-button>

        <mybtn>自定义按钮</mybtn>
        <button type="button" class="mui-btn mui-btn-royal">紫色</button>
    </div>



</template>
<script>
    import {Toast} from 'mint-ui'
    export default {
        data () {
            return {
                toastInstant:null
            }
        },
        created(){
            this.getList();
        },
        methods:{
            //模拟获取数据列表的Ajax方法
            getList(){
                //获取数据之前，弹出提示正在加载数据
                this.show();
                //数据加载成功后，3s后关闭提示
                setTimeout(() => {
                    this.toastInstant.close();
                },3000)
            },
            show(){
                this.toastInstant = Toast({
                    message:'操作',
                    position:'middle',
                    duration:-1,
                    iconClass: 'glyphicon glyphicon-ok',  //设置图标类
                    className:'mytotast'             //设置自定义样式
                })
            }
        }
    }
</script>
<style>
</style>
