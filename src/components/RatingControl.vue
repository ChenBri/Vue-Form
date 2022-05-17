<template>
    <ul>
        <li :class="{active: modelValue === 'poor'}">
            <button type="button" @click="activate('poor')">Poor</button>
        </li>
        <li :class="{active: modelValue === 'average'}">
           <button type="button" @click="activate('average')">Average</button>
        </li>
        <li :class="{active: modelValue === 'great'}">
            <button type="button" @click="activate('great')">Great</button>
        </li>
    </ul>
</template>
<script>
export default {
    props:[
        'modelValue'
    ],
    emits: [
        'update:modelValue'
    ],
    methods:{
        activate(option){
            this.$emit('update:modelValue', option)
        }
    }
}
</script>

<style scoped>
.active{
    border-color: purple;
}

.active button {
    color: purple;
}


</style>