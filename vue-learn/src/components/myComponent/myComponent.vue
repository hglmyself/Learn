<template>
    <Tabs>
        <TabPane label="Input输入条件框" icon="logo-windows">
            <div id="div" style="width:50%">
                <div class="search-con search-con-top">
                    <Input search enter-button="Search" placeholder="Enter something..." />
                    <Select v-model="searchKey" class="search-col">
                        <Option>China No.1</Option>
                        <Option>China No.1</Option>
                        <Option>China No.1</Option>
                    </Select>
                </div>
            </div>
        </TabPane>
        <TabPane label="List列表" icon="logo-apple"><Table :columns="columns1" :data="data1"></Table></TabPane>
        <TabPane label="Cascader 级联选择" icon="logo-tux"><Cascader :data="data" v-model="value1"></Cascader></TabPane>
    </Tabs>
</template>
<script>
    export default {
        name:"Tables",
        props:{
            columns: {
            type: Array,
            default () {
                return ["China"]
            }
        },
    },
    data(){
        return{
            insideColums:[],
            columns1: [
                    {
                        title: '姓名',
                        key: 'name'
                    },
                    {
                        title: '年龄',
                        key: 'age'
                    },
                    {
                        title: '住址',
                        key: 'address'
                    }
                ],
                data1: [
                    {
                        name: '黄光亮',
                        age: 18,
                        address: 'China No.1 Street',
                        date: '2019-08-22'
                    },
                    {
                        name: 'Alan',
                        age: 24,
                        address: 'China Lake Park',
                        date: '2019-08-22'
                    }
                ],
                value1: [],
                data: [{
                    value: 'beijing',
                    label: '北京',
                    children: [
                        {
                            value: 'gugong',
                            label: '故宫'
                        },
                        {
                            value: 'tiantan',
                            label: '天坛'
                        },
                        {
                            value: 'wangfujing',
                            label: '王府井'
                        }
                    ]
                }, {
                    value: 'jiangsu',
                    label: '江苏',
                    children: [
                        {
                            value: 'nanjing',
                            label: '南京',
                            children: [
                                {
                                    value: 'fuzimiao',
                                    label: '夫子庙',
                                }
                            ]
                        },
                        {
                            value: 'suzhou',
                            label: '苏州',
                            children: [
                                {
                                    value: 'zhuozhengyuan',
                                    label: '拙政园',
                                },
                                {
                                    value: 'shizilin',
                                    label: '狮子林',
                                }
                            ]
                        }
                    ],
                }]
            }

        }
    }
</script>

