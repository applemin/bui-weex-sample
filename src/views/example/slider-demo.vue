<template>
    <div @viewappear="onappear">
        <bui-header
                title="图片轮播"
                :leftItem="leftItem"
                @leftClick="back">
        </bui-header>


        <bui-image-slider :items="itemList" @itemClick="onItemClick" @change="onChange">
        </bui-image-slider>

    </div>

</template>

<style lang="sass" src="bui-weex/src/css/buiweex.scss"></style>

<script>
    var buiweex = require("bui-weex");
    export default {
        data: function () {
            return {
                leftItem: {
                    icons: 'icon-back',
                },
                itemList: [
                    {
                        url: 'https://gd2.alicdn.com/bao/uploaded/i2/T14H1LFwBcXXXXXXXX_!!0-item_pic.jpg'
                    },
                    {
                        url: 'https://gd1.alicdn.com/bao/uploaded/i1/TB1PXJCJFXXXXciXFXXXXXXXXXX_!!0-item_pic.jpg'
                    },
                    {
                        url: 'https://gd3.alicdn.com/bao/uploaded/i3/TB1x6hYLXXXXXazXVXXXXXXXXXX_!!0-item_pic.jpg'
                    },
                    {
                        url: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1491837948&di=3dcecd1b1d709196873a91f9fd585962&imgtype=jpg&er=1&src=http%3A%2F%2Fphotocdn.sohu.com%2F20160304%2Fmp61863731_1457078539188_3.gif'
                    }
                ]
            }
        },
        components: {
            "bui-image-slider": buiweex.buiImageSlider
        },
        methods: {
            "back": function () {
                buiweex.pop();
            },
            "onChange": function (e) {
                console.log(e);
            },
            "onItemClick": function (e, index) {
                console.log(index);
                console.log(e);
            }
        }
    }
</script>
<style>

</style>