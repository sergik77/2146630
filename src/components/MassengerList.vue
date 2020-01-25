<template>
    <div>
        <ul>
            <MessengerItem
            v-for="msn of messeng"
            v-bind:msn="msn"
            />
        </ul>
    </div>
</template>

<script>
    import MessengerItem from "./MessengerItem";
    export default {
        props: ['messeng'],
        name: "MassengerList",
        components: {MessengerItem}
    }
</script>

<style scoped>

</style>
