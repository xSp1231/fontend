<template>
    <div class="background">
        <!-- <div class="intro">
            <h2 style="text-align: center;">全民阅读 从儿童开始</h2>
        </div> -->
        <div class="intro">
                        <img style="width: 35%; height: 100%;margin-left: 30%;"
                        src="@/assets/image/font.png">
        </div>

        <div class="lunbo"><!----轮播图---->
            <el-carousel :interval="3900" type="card"  height="430px" style="margin-left: 5%;margin-right: 5%;">

                <el-carousel-item style="width: 1000px;">
                    <img style="width: 100%; height: 100%;"
                        src="@/assets/image/新闻1.jpg">
                </el-carousel-item>
                <el-carousel-item style="width: 1000px;">
                    <img style="width: 100%; height: 100%;"
                        src="@/assets/image/新闻2.jpg">
                </el-carousel-item>
                <el-carousel-item style="width: 1000px;">
                    <img style="width: 100%; height: 100%;"
                        src="@/assets/image/新闻3.jpg">
                </el-carousel-item>
                <el-carousel-item style="width: 1000px;">
                    <img style="width: 100%; height: 100%;"
                        src="@/assets/image/新闻4.jpg">
                </el-carousel-item>
                <el-carousel-item style="width: 1000px;">
                    <img style="width: 100%; height: 100%;"
                        src="@/assets/image/新闻5.jpg">
                </el-carousel-item>
               
            </el-carousel>
        </div>
        <div class="graph">
            <div class="graph1">
                <el-card style="width: 100%;; margin-left: 20px;" shadow="hover">
                   <graph1></graph1>
                </el-card>
            </div>
            <div class="graph2">
                <el-card style="width: 100%; margin-left: 20px;" shadow="hover">
                   <graph2></graph2>
                </el-card>
            </div>
        </div>
    </div>
</template>
<script>
import graph1 from './graph1.vue'
import graph2 from './graph2.vue'
export default {
    components: {
    graph1,
    graph2
  },
    data() {
        return {

        }
    },
    methods: {

    }
}
</script>
<style scoped>
 

.background {
    width: 100%;
    height: 100%;
}

.intro {
    position: relative;
    height: 6%;
    width: 100%;
}

.lunbo {
    position: relative;
    height: 50%;
    width: 100%;
}

.graph {
    display: flex;
    position: relative;
    height: 42%;
    width: 100%;

}

.graph1 {
    display: flex;
    position: relative;
    height: 100%;
    width: 50%;
}
.graph2 {
    display: flex;
    position: relative;
    height: 100%;
    width: 50%;
}
</style>
