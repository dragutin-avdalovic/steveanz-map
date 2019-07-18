<template>
    <div class="sidebar">
        <el-collapse v-model="activeNames" @change="handleChange">
            <el-collapse-item title="Route information" name="1">
                <span id="sport_icon" class="cross-country-skiing35 " title="running"></span>
                <el-select v-model="value" filterable placeholder="Select sport">
                    <el-option
                            v-for="item in options"
                            :key="item.value"
                            :label="item.label"
                            :value="item.value"
                            @click="selectItem(item.value)">
                    </el-option>
                </el-select>
            </el-collapse-item>
            <el-collapse-item title="Draw Route" name="2">
            </el-collapse-item>
            <el-collapse-item title="Edit Route" name="3">
            </el-collapse-item>
            <el-collapse-item title="Graphs" name="4">
            </el-collapse-item>
            <el-collapse-item title="Preferences" name="4">
            </el-collapse-item>
        </el-collapse>
    </div>
</template>

<script>
    /* eslint-disable no-console */

    export default {
        name: "Sidebar",
        data() {
            return {
                activeNames: ['1'],
                label: 'Select sport',
                options: [{
                    value: 'Running',
                    label: 'Running'
                }, {
                    value: 'Walking',
                    label: 'Walking'
                }, {
                    value: 'Cycling',
                    label: 'Cycling'
                }, {
                    value: 'Mountain biking',
                    label: 'Mountain biking'
                },
                {
                    value: 'Swimming',
                    label: 'Swimming'
                },
                {
                    value: 'Canoeing',
                    label: 'Canoeing'
                },
                {
                    value: 'Horse riding',
                    label: 'Horse riding    '
                },
                {
                    value: 'Downhill skiing',
                    label: 'Downhill skiing'
                },
                {
                    value: 'Cross-country skiing',
                    label: 'Cross-country skiing'
                }],
                value: 'Running'
            };
        },
        methods: {
            handleChange(val) {
                console.log(val);
            },
            selectItem(val){
                console.log('kakkasd');
                console.log(val);
            }
        }
    }
</script>

<style scoped>
    .sidebar {
        width: 20%;
        height: 100vh;
        outline: 0;
        font-size: 100%;
        vertical-align: baseline;
        background: transparent;
    }
    el-collapse {
       text-align: center;
    }
    el-collapse-item {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
    }
    .sport35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/running.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .walking35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/walking.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .cycling35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/cycling.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .mountain-biking35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/mountain-biking.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .swimming35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/swimming.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .canoeing35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/canoeing.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .horse-riding35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/horse-riding.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .downhill-skiing35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/downhill-skiing.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .cross-country-skiing35 {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/cross-country-skiing.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
</style>
