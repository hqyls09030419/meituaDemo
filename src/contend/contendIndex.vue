<template>
    <div class="contend-Iindex">
        <el-row>
            <!--内容导航部分-->
            <el-col :span="5">
                <left-bar />
            </el-col>
            <el-col :span="19" class="right-bar">
                <rigth-bar />
            </el-col>
        </el-row>
        <!--内容区域-->
            <el-col :span="24" class="list">
                <list-nav />
            </el-col>
        <div>
            <div class="list-components">
                <div class="list-nav">
                    <ul @mouseover="over">
                        <li class="item list-title">有格调</li>
                        <li :class="{item:true,active: isActive == 'all'}" data-type="all">全部</li>
                        <li :class="{item:true,active: isActive == 'food'}" data-type="all">约会聚餐</li>
                        <li :class="{item:true,active: isActive == 'spa'}" data-type="all">丽人SPA</li>
                        <li :class="{item:true,active: isActive == 'dy'}" data-type="all">电影演出</li>
                        <li :class="{item:true,active: isActive == 'cy'}" data-type="all">品质出游</li>
                        <li>丽人SPA</li>
                    </ul>
                </div>
                <div class="list-contend">
                    <el-col :span="7" class="list-nr" v-for="(item,index) in commodityList " :key="index">
                        <img  class="list-img" style="width: 100%" :src=item.url alt="">
                        <div class="list-contend-title">{{item.title}}</div>
                        <div class="list-vice">{{item.contend}}</div>
                        <div class="list-price">
                            <span class="price">￥{{item.price}}</span>
                            <span class="pre">/人均</span>
                        </div>
                    </el-col>

                </div>
            </div>
        </div>
        <el-row>
        </el-row>
    </div>
</template>
<script>
    import leftBar from  '../contend/leftBar'
    import rigthBar from  '../contend/rigthBar'
    import ListNav from '../contend/ListComponents'
    export  default {
        name:'contendIndex',
        components:{
            leftBar,
            rigthBar,
            ListNav
        },
        data(){
            return{

            }
        },
        methods:{
            over(){
                console.log('---')
            }
        }
    }

</script>

<style scoped>
    .contend-Iindex{
        width: 80%;
        margin: 0 auto;
    }
    /*.right-bar{*/
        /*width: 100%;*/
    /*}*/
</style>

