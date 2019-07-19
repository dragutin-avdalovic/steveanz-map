<template>
    <div class="sidebar">
        <el-collapse v-model="activeNames" @change="handleChange">
            <el-collapse-item title="Route information" name="1">
                <span id="sport_icon" :class="sportClass" title="running" ref="sport-icon"></span>
                <el-select @change="handleChange" :value="value" filterable placeholder="Select sport">
                    <el-option
                            v-for="item in options"
                            :key="item.value"
                            :label="item.label"
                            :value="item.value">
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
                    value: 'running',
                    label: 'Running'
                }, {
                    value: 'walking',
                    label: 'Walking'
                }, {
                    value: 'cycling',
                    label: 'Cycling'
                }, {
                    value: 'mountain_biking',
                    label: 'Mountain biking'
                },
                {
                    value: 'swimming',
                    label: 'Swimming'
                },
                {
                    value: 'canoeing',
                    label: 'Canoeing'
                },
                {
                    value: 'horse_riding',
                    label: 'Horse riding    '
                },
                {
                    value: 'downhill_skiing',
                    label: 'Downhill skiing'
                },
                {
                    value: 'cross-country_skiing',
                    label: 'Cross-country skiing'
                }],
                value: 'Running',
                prevSelected: 'Running',
                sportClass: 'running'
            };
        },
        methods: {
            handleChange: function (selected) {
                this.value = selected;
                this.sportClass = selected;
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
    .running {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/running.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .walking {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/walking.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .cycling {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/cycling.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .mountain_biking {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/mountain-biking.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .swimming {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/swimming.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .canoeing {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/canoeing.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .horse_riding{
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/horse-riding.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .downhill_skiing {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/downhill-skiing.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.7);
        }
    .cross-country_skiing {
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
