<template>
    <div>
        <tab :line-width=2 active-color='#fc378c' v-model="index">
            <tab-item class="vux-center" v-for="(item, index) in list" @click="sel = item" :key="index" :selected="sel === item"> {{ item }} </tab-item>
        </tab>
        <swiper v-model="index" height="420px" :show-dots="false">
            <swiper-item v-for="(catItem, catIndex) in menu" :key="catIndex">
                <div class="tab-swiper vux-center">
                    <grid>
                        <grid-item :label="ct.str" v-for="(ct, ci) in catItem" :key="ci" @on-item-click="toast(ct.str)">
                            <img slot="icon" :src="ct.img">
                        </grid-item>
                    </grid>
                </div>
            </swiper-item>
        </swiper>
        <toast v-model="toastShow" type="text">{{ toastStr }}</toast>
    </div>
</template>

<script>
    import { Tab, TabItem, Swiper, SwiperItem, Grid, GridItem, Toast } from 'vux';

    export default {
        data () {
            return {
                index: 0,
                toastShow: false,
                toastStr: '',
                sel: '小型',
                list: ['小型', '中型', '大型'],
                menu: [
                    [
                        { str: '新加坡猫', img: 'https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=885744084,3886146253&fm=5' },
                        { str: '柯尼斯卷毛猫', img: 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=1855682282,311511202&fm=5' },
                        { str: '东方猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1891064581,255096779&fm=5' }
                    ],
                    [
                        { str: '苏格兰折耳猫', img: 'https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=1569462993,172008204&fm=5' },
                        { str: '英国短毛猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1667994205,255365672&fm=5' },
                        { str: '波斯猫', img: 'https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=1853832225,307688784&fm=5' },
                        { str: '俄罗斯蓝猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1949962039,312600035&fm=5' },
                        { str: '美国短毛猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=2406161785,701397900&fm=5' },
                        { str: '异国短毛猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=2244238741,1217077712&fm=5' },
                        { str: '挪威森林猫', img: 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=1917461690,696184102&fm=5' }
                    ],
                    [
                        { str: '布偶猫', img: 'https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=2247692397,1189743173&fm=5' },
                        { str: '英国短毛猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=1667994205,255365672&fm=5' },
                        { str: '美国短毛猫', img: 'https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=2406161785,701397900&fm=5' },
                        { str: '沙特尔猫', img: 'https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=2199312764,1078124651&fm=5' }
                    ]
                ]
            };
        },
        components: {
            Tab,
            TabItem,
            Swiper,
            SwiperItem,
            Grid,
            GridItem,
            Toast
        },
        methods: {
            toast (str) {
                this.toastStr = str;
                this.toastShow = true;
            }
        }
    };
</script>

<style lang="less">
    .weui-grid{text-decoration: none;
        .weui-grid__icon{
            width: 60px;height: 60px;
            img{border-radius: 50%;}
        }
    }
</style>
