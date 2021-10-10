<template>
    <div>
        <div v-for="(config, i) in configFields" :key="config.id">
            <input v-show="i + 1 < configFields.length" v-model="config.machine"/>
            <input v-model.lazy="config.id" />
        </div>
        <button @click="addConfig">Add</button>
        <hr/>
        {{ configAsString }}
    </div>
</template>

<script>
    export default {
        data() {
            return {
                configFields: [{ machine: 'Machine 1', id: '0' }]
            }
        },
        computed: {
            configAsString () {
                return this.getConfigString(this.configFields); 
            }
        },
        methods: {
            addConfig () {
                const length = this.configFields.length;
                this.configFields.push({ machine: `Machine ${length + 1}`, id: length + '' })
            },
            
            getConfigString(configs) {
                if (!configs.length)
                    return '';
                
                const { machine, id } = configs[0];

                if (configs.length == 1)
                    return `${id}`;

                return `#{if Octopus.Machine.Id == "${machine}"}${id}#{else}${this.getConfigString(configs.slice(1))}#{/if}`
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>