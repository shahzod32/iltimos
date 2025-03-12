<template>
    <Input class="search-input" placeholder="Kinolarni qidirish" v-model="term" @input="changeHandler"/>
</template>
<script>
import Input from '@/ui-components/Input.vue';

export default {
    props: {
        updateTermHandler: {
            type: Function,
            required: true,
        },
    },
    data() {
        return {
            term: '', 
        }
    },
    methods: {
        changeHandler(e) {
            this.term = e.target.value,
            this.updateTermHandler(this.term)
        },
    },
}
</script>
<style scoped>
    search-input{
        padding: 1.5rem;
        background-color: #fcfaf5;
        margin-bottom: 1.5rem;
        border-radius: 4px;
        box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
    }
</style>