<template lang="html">
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <form action="">
                <label>Quote</label>
                <textarea class="form-control" v-model="quote"></textarea>
            </form>
            <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                this.$emit('quoteToAdd', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style lang="css">
</style>
