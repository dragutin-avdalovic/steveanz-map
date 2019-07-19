<template>
    <div class="sidebar">
        <el-collapse v-model="activeNames" @change="handleChangeNames">
            <el-collapse-item title="Route information" name="1">
                <div class="collapse-row">
                    <span id="sport_icon" :class="sportClass" title="running" ref="sport-icon"></span>
                    <el-select @change="handleChange" :value="value" filterable placeholder="Select sport">
                    <el-option
                            v-for="item in options"
                            :key="item.value"
                            :label="item.label"
                            :value="item.value">
                    </el-option>
                </el-select>
                </div>
                <div class="collapse-row">
                    <span id="distance" class="distance" title="distance"></span>
                    <p><span class="label">distance</span><br>
                        <span class="value distance_val" id="distanceElem">0.00</span>
                        <span class="unit distance_unit"> ml</span>
                    </p>
                </div>
                <div class="collapse-row">
                    <span id="energy" class="energy" title="energy"></span>
                    <p><span class="label">energy</span><br>
                        <span class="value energy_val" id="energyElem">0</span>
                        <span class="unit energy_unit">kcal</span>
                    </p>
                </div>
            </el-collapse-item>
            <el-collapse-item title="Draw Route" name="2">
                <el-row class="row-btns">
                    <el-checkbox v-model="checked1" label=" Follow roads" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-search" circle></el-button>
                    <el-button type="primary" icon="el-icon-edit" circle></el-button>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-check" circle></el-button>
                    <el-button type="primary" icon="el-icon-message" circle></el-button>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-star-off" circle></el-button>
                    <el-button type="info" icon="el-icon-delete" circle></el-button>
                </el-row>
            </el-collapse-item>
            <el-collapse-item title="Edit Route" name="3">
                <el-row class="row-btns">
                    <el-checkbox v-model="checked1" label=" Follow roads" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-search" circle></el-button>
                    <el-button type="primary" icon="el-icon-edit" circle></el-button>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-check" circle></el-button>
                    <el-button type="primary" icon="el-icon-message" circle></el-button>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-star-off" circle></el-button>
                    <el-button type="info" icon="el-icon-delete" circle></el-button>
                </el-row>
            </el-collapse-item>
            <el-collapse-item title="Graphs" name="4">
                <el-row class="row-btns">
                    <el-checkbox v-model="checked1" label="Show elevation" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                <el-checkbox v-model="checked1" label="Show gradient" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                    <el-button type="primary" icon="el-icon-star-off"> Refresh elevation</el-button>
                </el-row>
            </el-collapse-item>
            <el-collapse-item title="Preferences" name="4">
                <el-row class="row-btns">
                    <el-checkbox v-model="checked1" label="Distance markers" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                    <el-checkbox v-model="checked1" label="Auto-scroll map" border></el-checkbox>
                </el-row>
                <el-row class="row-btns">
                    <el-radio-group v-model="radio2">
                        <el-radio-button label="mile"></el-radio-button>
                        <el-radio-button label="km"></el-radio-button>
                        <el-radio-button label="kcal"></el-radio-button>
                        <el-radio-button label="kJ"></el-radio-button>
                    </el-radio-group>
                </el-row>
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
                sportClass: 'running',
                checked1: false
            };
        },
        methods: {
            handleChange: function (selected) {
                this.value = selected;
                this.sportClass = selected;
            },
            handleChangeNames: function (selected) {
                this.activeNames = selected;
            }
        }
    }
</script>

<style scoped>
    .sidebar {
        width: 25%;
        height: 100vh;
        outline: 0;
        font-size: 100%;
        vertical-align: baseline;
        background: transparent;
        max-height: 100vh;
        overflow: auto;
    }
    el-collapse {
       text-align: center;
    }
    el-collapse-item {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
    .collapse-row {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
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
    .distance {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/distance.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.9);
        }
    .energy {
        display: inline-block;
        width: 65px;
        height: 65px;
        background-image: url(../assets/images/energy.png);
        background-repeat: no-repeat;
        padding: 0!important;
        margin-right: 10px;
        transform: scale(0.9);
        }
    .collapse-row {
        align-items: center;
    }
    .label {
        font-size: 1.1em;
        font-style: italic;
    }
    .value {
        font-size: 1.6em;
        font-weight: bold;
        color: #888;
    }
    .unit {
        font-size: 1.1em;
        font-weight: bold;
        color: #777;
    }
    .row-btns {
        width: 100%;
        padding: 10px;
    }
    .row-btns .el-checkbox {
        font-size: 1.1em;
        font-weight: bold;
        color: #777;
    }
</style>
