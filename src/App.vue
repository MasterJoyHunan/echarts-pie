<template>
    <v-chart key="xyw-chart"
             ref="xywChartRef"
             :option="xywOption"
             autoresize />
</template>

<script setup>
import { ref } from 'vue'
import { use } from 'echarts/core'
import { SVGRenderer } from 'echarts/renderers'
import { PieChart } from 'echarts/charts'
import { GridComponent } from 'echarts/components'
import VChart from 'vue-echarts'
use([SVGRenderer, PieChart, GridComponent])

const xywOption = ref({
    series: [
        {
            type: 'pie',
            radius: [135, 200],
            animationDuration: 3000,
            label: {
                show: true,
                color: 'inherit',
                fontSize: 20,
                formatter: ({ dataIndex, color, percent }) => {
                    return percent + '%'
                }
            },
            labelLine: {
                length: 20,
                length2: 60
            },
            itemStyle: {
                borderWidth: 8,
                borderColor: '#fff'
            },
            data: [
                {
                    name: '长沙',
                    value: 15
                },
                {
                    name: '株洲',
                    value: 4
                },
                {
                    name: '湘潭',
                    value: 1
                },
                {
                    name: '永州',
                    value: 1
                },
                {
                    name: '邵阳',
                    value: 2
                },
                {
                    name: '张家界',
                    value: 1
                },
                {
                    name: '怀化',
                    value: 1
                },
                {
                    name: '郴州',
                    value: 1
                },
                {
                    name: '衡阳',
                    value: 1
                },
                {
                    name: '合肥',
                    value: 8
                },
                {
                    name: '郑州',
                    value: 8
                }
            ]
        }
    ]
})

</script>

<style>
html,
body {
    width: 100%;
    height: 100%;
}
#app {
    width: 100%;
    height: 100%;
}
</style>
