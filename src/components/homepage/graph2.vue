<template>
    <div ref="graph2" style="width: 100%; height: 260px;"></div>
</template>
<script>
import * as echarts from 'echarts/core';
import 'echarts/theme/macarons.js'
export default {
    data() {
        return {}
    },
    mounted() {
        this.init2();
    },
    methods: {
        init2() {
            var myChart = echarts.init(this.$refs.graph2, 'macarons');
        var  option = {
                title: {
                    text: '中国父母为孩子选书上的困扰'
                },
                tooltip: {
                    trigger: 'axis',
                    textStyle : {
            color: 'white',
            decoration: 'none',
            fontFamily: 'Verdana, sans-serif',
            // fontStyle: 'italic',
            fontWeight: 'bold'
        },
                    formatter: function (params) {
                        console.log(params);
                    var relVal = params[0].name
            for (var i = 0, l = params.length; i < l; i++) {
              relVal += '<br/>' + params[i].marker + '比值' + ' : ' + params[i].value + ' % '
            }
            return relVal
                }
                    // axisPointer: {
                    // type: 'shadow'
                    // }
                },
                legend: {},
                grid: {
                    left: '10%',
                    right: '4%',
                    top: '10%',
                    bottom:'10%'
                    // containLabel: true
                },
                xAxis: {
                    type: 'value',
                    show:false
                },
                yAxis:[{
                    type: 'category',
                    data: ['top1书目太多不知道怎么选书', 'top2我选的书孩子不爱读，孩子选的书我不认同', 'top3不知道去哪儿找专业的书单', 'top4书单没发在同一平台找到', 'top5推荐的书单高于孩子的阅读水平', 'top6书单推荐的书不知道去哪买','top7推荐的书单低于孩子的阅读水平','top8我没有为孩子选书的困扰','top9其他'],
                    axisLine:{
                    show:false
                    },
                    axisTick:{
                    show:false
                    },
                    // axisLabel:{
                    // color:'#ff3333'
                    // },
                     axisLabel: {
                        color:'#ff3333',
              margin: 20, //x轴距离文字距离
              interval: 0, //使x轴文字显示全
              rotate: 0, //文字倾斜
              formatter: function (value) {
                let valueTxt = "";
                if (value.length > 3) {
                  valueTxt = value.substring(0, 4) ;
                } else {
                  valueTxt = value;
                }
                return valueTxt;
              },
            },

                }],
                series: [
                    {
                    type: 'bar',
                    data: [50.0, 34.3, 32.2, 31.8, 31.0, 25.5,23.9,5.7,0.2],
                    itemStyle: {
                    normal: {
                        color: new echarts.graphic.LinearGradient(1, 0, 0, 0, [{  
                // 四个数字分别对应 数组中颜色的开始位置，分别为 右，下，左，上。例如（1,0,0,0 ）代表从右边开始渐
                // 变。offset取值为0~1，0代表开始时的颜色，1代表结束时的颜色，柱子表现为这两种颜色的渐变。
                        offset: 0,
                        color: '#FFA54F'
                        }, {
                        offset: 1,
                        color: '#ff3333'
                        }]),barBorderRadius: 20
                    }
                    },
                    barCategoryGap: 50,
                    barWidth:15,
                    label: {
                        show:true,
                        position:"inside",
                        formatter:"{c}%"
                    }
                    }
                ]
                };
            myChart.setOption(option);
        }
    },
};
</script>
