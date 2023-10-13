<template>
    <div id="app">
        <input type="text" v-model="name" />
        <input type="text" id="surname" value="Snow" />
        <button @click="saveSurname">Save Surname</button>
        <h1>{{ computedFullName }}</h1>
        <hr />
        <ul>
            <li v-for="(exp, i) in non생선" :key="i">
                {{ exp.name }} ({{ exp.cost }})
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "App",
    components: {},
    data() {
        return {
            name: "John",
            surname: "",
            experiments: [
                { name: "가나다", cost: 650, field: "생선" },
                { name: "라마바", cost: 650, field: "생선" },
                { name: "사아자", cost: 650, field: "고기" },
                { name: "차카타", cost: 650, field: "생선" },
                { name: "파하", cost: 650, field: "고기" },
            ],
        };
    },
    computed: {
        computedFullName() {
            return this.name + "" + this.surname;
        },
        non생선() {
            return this.experiments.filter((exp) => exp.field !== "생선");
        },
    },
    methods: {
        saveSurname() {
            this.surname = this.$el.querySelector("#surname").value;
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
