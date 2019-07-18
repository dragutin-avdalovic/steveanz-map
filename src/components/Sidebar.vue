<template>
    <div class="sidebar">
        <el-collapse v-model="activeNames" @change="handleChange">
            <el-collapse-item title="Route information" name="1">
                <el-select v-model="value" filterable placeholder="Select sport">
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
</style>
