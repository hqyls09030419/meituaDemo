<!--  首页 列表-->
<template>
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
</template>

<script>
    export default {
        data() {
            return {
                isActive: 'all',
                commodityList:[
                    {
                        url:"//p0.meituan.net/msmerchant/1a8aaac8cfcf76fae83c2ecd6405bd4c1457315.jpg@368w_208h_1e_1c",
                        title: '金逸影城（会聚IMXA店',
                        contend: "免押金,可停车,儿童票,有WIFI,双机3D厅,4DX厅",
                        price: '19.9'
                    },
                    {
                        url:'//p1.meituan.net/deal/bd9a5c59a6646c683b214139056b7fe1332966.jpg@368w_208h_1e_1c',
                        title:'正华影城',
                        contend: "免押金,可停车,儿童票,有WIFI,双机3D厅,4DX厅",
                        price:'19.9'
                    }
                    ,
                    {
                        url:'//p1.meituan.net/deal/bd9a5c59a6646c683b214139056b7fe1332966.jpg@368w_208h_1e_1c',
                        title:'正华影城',
                        contend: "免押金,可停车,儿童票,有WIFI,双机3D厅,4DX厅",
                        price:'19.9'
                    }
                ]
            }
        },
        methods:{
            over(){

            }
        }


    }
</script>

<style scoped>
    .list-components {
        /*border: 1px solid;*/
        margin: 40px auto;
    }

    .list-nav {
        width: 100%;
        height: 50px;
        line-height: 44px;
        box-sizing: border-box;
        font-size: 14px;
        color: #fff;
        border-top-right-radius: 5px;
        border-top-left-radius: 5px;
        background-color: rgb(190, 164, 116);
        background-image: linear-gradient(to right, rgb(194, 176, 142) 3%, rgb(190, 164, 116) 100%);
    }

    .list-nav ul > .item{
        float: left;
        padding: 0 10px;
        position: relative;
        cursor: pointer;
        text-transform: uppercase;
    }

    .list-title {
        font-size: 21px;
        font-weight: 600;
        margin-left: 25px;
        margin-right: 15px;
    }
    .active:after{
        display:block;
        content:'';
        border-width:8px 8px 8px 8px;
        border-style:solid;
        border-color: transparent transparent #fff transparent;

        /* 定位 */
        position:absolute;
        left:40%;
        top:34px;
    }
    .list-contend{
        width: 100%;
        background-color: #fff;
        border: 1px solid ;
        box-sizing: border-box;
    }
    .list-contend:after{
        clear: both;
        content: "";
        width: 0;
        height: 0;
        display: block;
        visibility: hidden;
    }
    .list-nr{
        margin-top: 10px;
        margin-left: 40px;
        margin-bottom: 10px;
    }
    .list-contend-title{
        font-size: 18px;
        color: #222;
        height: 22px;
        line-height: 22px;
        font-weight: 500;
        margin-top: 10px;
        margin-bottom: 10px;
        white-space: nowrap;
        overflow: hidden;
        cursor: pointer;
        text-overflow:ellipsis;
    }
    .list-vice{
        font-size: 12px;
        color: #999;
        line-height: 18px;
        margin-bottom: 15px;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
    .list-price{
        margin-bottom: 5px;
        height: 27px;
        overflow: hidden;
    }
    .price{
        font-size: 25px;
        color: #BE9E4D;
        font-weight: 800;
    }
    .pre{
        font-size: 14px;
        color: #be9e4d;

    }
    .list-img{
        border-right: 5px;
    }
</style>

