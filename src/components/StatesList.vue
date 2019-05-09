<template>
    <div>
        <p> Initialize diffusion constants</p>
        <ol>
          <SingleState
           v-for="state in states"
           :state="state"
           :key="state.id"
           @rm="removeState"
           ></SingleState>
        </ol>
        <button @click="addState" v-if="allow">Add state</button>
        <button @click="run"> Run analysis </button>
    </div>
</template>

<script>
import SingleState from './SingleState.vue'
var curid = 0

export default {
    components: {SingleState},
    data () {return {states: [
        {id: curid++, title: 'Bound', diffusionConstant: 0, fraction: 50},
        {id: curid++, title: 'Free', diffusionConstant: 0.05, fraction: 50},
    ]}
    },
    computed: {allow () {return this.states.length < 3}},
    methods: {
        run : function (){
            console.log(this.states)
        },
        removeState : function(id){
            if(this.states.length > 1){
                console.log('removing ' + id)
                this.states = this.states.filter(state => {return state.id != id})
            }else{
                console.log('can\'t remove last item')
            }
        },
        sumFractions : function (){
            let sum = 0
            for(let i = 0; i < this.states.length; i++){
                sum += this.states[i].fraction
                }
            return sum
        },

        addState : function(){
            console.log('Add state ' + String(curid + 1))
            console.log('sum fractions: ' + this.states.reduce((a,b) => (a.fraction + b.fraction)))
            this.states.push({id: curid++, 
                              title: 'New state', 
                              diffusionConstant: 0.1, 
                              fraction: 100 - this.sumFractions()
                            //   function() {
                            //       sum = this.states.reduce((a,b) => (a.fraction + b.fraction))
                            //       console.log('sum ' + sum)
                            //       return 100 - sum
                            //   }
                            })
        }
    }   
}
</script>
