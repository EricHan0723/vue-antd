<style scoped>
    .layout{
        border: 1px solid #d7dde4;
        background: #f5f7f9;
        position: relative;
    }
    .layout-breadcrumb{
        padding: 10px 15px 0;
    }
    .layout-content{
        min-height: 200px;
        margin: 15px;
        overflow: hidden;
        background: #fff;
        border-radius: 4px;
    }
    .layout-content-main{
        padding: 10px;
    }
    .layout-copy{
        text-align: center;
        padding: 10px 0 20px;
        color: #9ea7b4;
    }
    .layout-menu-left{
        background: #464c5b;
    }
    .layout-header{
        height: 60px;
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
    .layout-logo-left{
        width: 90%;
        height: 30px;
        background: #5b6270;
        border-radius: 3px;
        margin: 15px auto;
    }
</style>
<template>
    <div class="layout">
        <Row type="flex">
            <i-col span="5" class="layout-menu-left">
                <Menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
                    <div class="layout-logo-left"></div>
                    <Submenu name="1">
                        <template slot="title">
                            <Icon type="ios-navigate"></Icon>
                            导航一
                        </template>
                        <Menu-item name="1-1">选项 1</Menu-item>
                        <Menu-item name="1-2">选项 2</Menu-item>
                        <Menu-item name="1-3">选项 3</Menu-item>
                    </Submenu>
                    <Submenu name="2">
                        <template slot="title">
                            <Icon type="ios-keypad"></Icon>
                            导航二
                        </template>
                        <Menu-item name="2-1">选项 1</Menu-item>
                        <Menu-item name="2-2">选项 2</Menu-item>
                    </Submenu>
                    <Submenu name="3">
                        <template slot="title">
                            <Icon type="ios-analytics"></Icon>
                            导航三
                        </template>
                        <Menu-item name="3-1">选项 1</Menu-item>
                        <Menu-item name="3-2">选项 2</Menu-item>
                    </Submenu>
                </Menu>
            </i-col>
            <i-col span="19">
                <div class="layout-header"></div>
                <div class="layout-breadcrumb">
                    <Breadcrumb>
                        <Breadcrumb-item href="#">首页</Breadcrumb-item>
                        <Breadcrumb-item href="#">应用中心</Breadcrumb-item>
                        <Breadcrumb-item>某应用</Breadcrumb-item>
                    </Breadcrumb>
                </div>
                <div class="layout-content">
                    <div class="layout-content-main">
                        <Row>
                                <Col span="11">
                                    <Card>
                                        <p slot="title">标准卡片</p>
                                        <p>卡片内容</p>
                                        <p>卡片内容</p>
                                        <p>卡片内容</p>
                                    </Card>
                                </Col>
                                <Col span="11" offset="2">
                                    <Card dis-hover>
                                        <p slot="title">禁用悬停阴影的卡片</p>
                                        <p>卡片内容</p>
                                        <p>卡片内容</p>
                                        <p>卡片内容</p>
                                    </Card>
                                </Col>
                            </Row>
                        <div style="background:#eee;padding: 20px">
                            <Card :bordered="false">
                                <p slot="title">无边框标题</p>
                                <p>无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充。</p>
                            </Card>
                        </div>
                        <div style="background:#eee;padding: 20px">
                                                    <Card :bordered="false">
                                                        <p slot="title">无边框标题</p>
                                                        <p>无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充。</p>
                                                    </Card>
                                                </div>
                                                <div style="background:#eee;padding: 20px">
                                                                            <Card :bordered="false">
                                                                                <p slot="title">无边框标题</p>
                                                                                <p>无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充无边框内容填充。</p>
                                                                            </Card>
                                                                        </div>
                        <Card style="width:350px">
                            <p slot="title">
                                <Icon type="ios-film-outline"></Icon>
                                经典电影
                            </p>
                            <a href="#" slot="extra" @click.prevent="changeLimit">
                                <Icon type="ios-loop-strong"></Icon>
                                换一换
                            </a>
                            <ul>
                                <li v-for="item in randomMovieList">
                                    <a :href="item.url" target="_blank">{{ item.name }}</a>
                                    <span>
                                        <Icon type="ios-star" v-for="n in 4" :key="n"></Icon><Icon type="ios-star" v-if="item.rate >= 9.5"></Icon><Icon type="ios-star-half" v-else></Icon>
                                        {{ item.rate }}
                                    </span>
                                </li>
                            </ul>
                        </Card>
                    </div>
                </div>
                <div class="layout-copy">
                    2011-2016 &copy; TalkingData
                </div>
            </i-col>
        </Row>
        <Back-top></Back-top>
    </div>
</template>
<script>
    export default {
        data () {
                    return {
                        movieList: [
                            {
                                name: '肖申克的救赎',
                                url: 'https://movie.douban.com/subject/1292052/',
                                rate: 9.6
                            },
                            {
                                name: '这个杀手不太冷',
                                url: 'https://movie.douban.com/subject/1295644/',
                                rate: 9.4
                            },
                            {
                                name: '霸王别姬',
                                url: 'https://movie.douban.com/subject/1291546/',
                                rate: 9.5
                            },
                            {
                                name: '阿甘正传',
                                url: 'https://movie.douban.com/subject/1292720/',
                                rate: 9.4
                            },
                            {
                                name: '美丽人生',
                                url: 'https://movie.douban.com/subject/1292063/',
                                rate: 9.5
                            },
                            {
                                name: '千与千寻',
                                url: 'https://movie.douban.com/subject/1291561/',
                                rate: 9.2
                            },
                            {
                                name: '辛德勒的名单',
                                url: 'https://movie.douban.com/subject/1295124/',
                                rate: 9.4
                            },
                            {
                                name: '海上钢琴师',
                                url: 'https://movie.douban.com/subject/1292001/',
                                rate: 9.2
                            },
                            {
                                name: '机器人总动员',
                                url: 'https://movie.douban.com/subject/2131459/',
                                rate: 9.3
                            },
                            {
                                name: '盗梦空间',
                                url: 'https://movie.douban.com/subject/3541415/',
                                rate: 9.2
                            }
                        ],
                        randomMovieList: []
                    }
                },
                methods: {
                    changeLimit () {
                        function getArrayItems(arr, num) {
                            const temp_array = [];
                            for (let index in arr) {
                                temp_array.push(arr[index]);
                            }
                            const return_array = [];
                            for (let i = 0; i<num; i++) {
                                if (temp_array.length>0) {
                                    const arrIndex = Math.floor(Math.random()*temp_array.length);
                                    return_array[i] = temp_array[arrIndex];
                                    temp_array.splice(arrIndex, 1);
                                } else {
                                    break;
                                }
                            }
                            return return_array;
                        }
                        this.randomMovieList = getArrayItems(this.movieList, 5);
                    }
                },
                mounted () {
                    this.changeLimit();
                }
    }
</script>
