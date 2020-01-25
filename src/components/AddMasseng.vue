<template>
    <form v-on:submit.prevent="onSubmit">
        <b-textarea type="text"v-model="msg"></b-textarea>
        <button type="submit">Написать консультанту</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                msg: ''
            }
        },
        name: "AddMasseng",
        methods: {
            onSubmit() {
                console.log('Submit', this.msg)
                if (this.msg.trim()) {
                    const newMasseng = {
                        id: Date.now(),
                        msg: this.msg,
                        name: 'user',
                        data: '14 октября 2011'
                    }
                    this.$emit('add-masseng',newMasseng)
                    this.msg = ''
                }
            }
        }
    }
</script>

<style scoped>
    form {

        padding: 30px 0;
    }
button {text-align: center;
    margin: 22px auto;
    background-color: #fdd639;
    padding: 10px 55px;
    border-radius: 20px;
    border-color: transparent;
}
</style>
