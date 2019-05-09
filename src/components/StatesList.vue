<template>
    <div>
        <p> Initialize diffusion constants</p>
        <ol>
          <SingleState
           v-for="state in states"
           :state="state"
           :key="state.id"
           ></SingleState>
        </ol>
    </div>
</template>

<script>
import SingleState from './SingleState.vue'

export default {
    components: {SingleState},
    data () {return {states: [
        {id: 1, title: 'Bound state', diffusionConstant: 0, fraction: 30},
        {id: 2, title: 'Free state', diffusionConstant: 0.05, fraction: 30},
        {id: 3, title: 'Fast state', diffusionConstant: 0.1, fraction: 30},
    ]}
    }    
}
</script>
