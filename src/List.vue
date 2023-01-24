<template>
    <ul class="ul">
        <ListItem v-for="item in mylist" :key="item.id" :title="item.name"></ListItem>
    </ul>
</template>

<script>
import ListItem from './ListItem.vue';
export default{
    data() {
        return {
            mylist: [
                {
                    id: 1,
                    name: "listItem 1"
                },
                {
                    id: 2,
                    name: "listItem 2"
                },
                {
                    id: 3,
                    name: "listItem 3"
                }
            ]
        };
    },
    components: { ListItem }
}
</script>

<style scoped>

</style>