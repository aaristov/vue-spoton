<template>
    <li><input type='text' :value="state.title"> state:  
    <input :value="state.diffusionConstant">  um2/s, 
    fraction <input maxlength=2 :value="state.fraction"> % 
    <button @click="$emit('rm', state.id)">-</button></li>
</template>

<script>
export default {
    name: "SingleState",
    props: {
        state: Object
    }
}
</script>
