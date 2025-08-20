<template lang="">
    <div class="btn-group">
        <button class="btn btn-dark" @click='filterHandler'>Barcha kinolar</button>
        <button class="btn btn-outline-dark">Mashhur kinolar</button>
        <button class="btn btn-outline-dark">Eng ko'p ko'rilgan kinolar</button>
    </div>
</template>
<script>
export default {
    props: {
        updateFilterHandler: {
            type: Function,
            required: true,

        },
    },
    data() {
        return {
            filter : "all",
        }
    },

    methods : {
        filterHandler(filter) {

        }
    }
    
}
</script>
<style lang="">
    
</style>