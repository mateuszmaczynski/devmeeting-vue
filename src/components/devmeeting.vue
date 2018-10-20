<template>
    <div class="devmeeting" id="app">
        <ul>
            <li v-for="item in shoppingList" :key="item.id">
                {{ item.name }}
            </li>
        </ul>
        <button v-on:click="addProduct()">Dodaj</button>
        <input v-model="name" placeholder="name"/>
    </div>
</template>

<script>
    export default {
        name: 'devmeeting',
        data() {
            return {
                shoppingList: [
                    {
                        id: 1,
                        name: 'bread'
                    },
                    {
                        id: 2,
                        name: 'cheese'
                    },
                    {
                        id: 3,
                        name: 'mineral water'
                    }
                ],
                name: ""
            }
        },
        props: {
            msg: String,
        },
        methods: {
            addProduct() {
                let index = this.shoppingList[this.shoppingList.length] + 1;
                this.shoppingList.push({
                    id: index,
                    name: this.name
                })
            }
        }
    };
</script>

<style scoped></style>