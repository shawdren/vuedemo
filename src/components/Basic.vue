<template>
    <div class="basic">
        <router-link to="/">Home</router-link>
        <h1>{{ msg }}</h1>
        <h2>Data Binding</h2>
        <h3>One way</h3>
        <div>
            <p>{{ oneWay }}</p>
        </div>
        <h3>Tow way</h3>
        <div>
            <p>{{ twoWay }}</p>
            <input type="text" v-model="twoWay">
        </div>
        <hr>
        <h3>List rendering</h3>
        <div>
            <ul>
                <!--v-for-->
                <li v-for="item in fruits">{{ item }}</li>
                <!--argument for the index of the current item-->
                <li v-for="(item, index) in fruits">{{ item + ' - ' + index }}</li>
                <!--Range v-for -->
                <li v-for="n in 5">{{ n }}</li>
            </ul>
        </div>
        <hr>
        <h3>Conditional Rendering</h3>
        <div>
            <p>v-if and v-else</p>
            <h4 v-if="isLoggedIn">
                Welcome dear user
            </h4>
            <h4 v-else>
                Welcome Guest
            </h4>
            <p>v-show and v-model </p>
            <form>
                <p v-show="!title">
                    Please fill the title:
                </p>
                <input type="text" name="title" v-model="title">
                <button type="submit" v-show="title">Submit</button>
            </form>
        </div>
        <hr>
        <h3>Event</h3>
        <p> start with "v-on:", "@" is a shortcut for "v-on:"</p>
        <div>
            <button type="button" @click="alertMe">
                I'll alert you after you click me!
            </button>
        </div>
        <hr>
        <h3>Properties and Methods</h3>
        <div>
            <p> Computed properties </p>
            <h4>{{ fullName }}</h4>
            <p> Creating filters with computed properties </p>
            <h4>All Tasks:</h4>
            <ul>
                <li v-for="item in tasks">{{ item.title }}</li>
            </ul>

            <h4>Unfinished Tasks:</h4>
            <ul>
                <li v-for="item in unfinishedTasks">{{ item.title }}</li>
            </ul>
            <p> Methods</p>
            <p>counter:  {{counter }}</p>
            <button type="button" @click="increaseCounter">
                increaseCounter
            </button>
            <button type="button" @click="decreaseCounter">
                decreaseCounter
            </button>
        </div>
        <hr>
    </div>
</template>

<script>
    export default {
        name: 'basic',
        data() {
            return {
                msg: 'The demo of vue directive',
                oneWay: 'This is one way binding-{{}}',
                twoWay: 'This is tow way binding-(v-model)',
                fruits: [
                    'apple', 'orange', 'banana', 'watermelon'
                ],
                isLoggedIn: false,
                title: null,
                counter: 0,
                firstName: 'John',
                lastName: 'Doe',
                tasks: [
                    { id: 1, title: 'get up from bed', completed: true },
                    { id: 2, title: 'turn on the computer', completed: true },
                    { id: 3, title: 'open iTunes', completed: false },
                    { id: 4, title: 'Listen to some Pink Floyd', completed: false },
                    { id: 5, title: 'Go to bed', completed: false }
                ]
            }
        },

        computed: {
            fullName() {
                return this.firstName + ' ' + this.lastName;
            },
            unfinishedTasks() {
                return this.tasks.filter((item) => {
                    return item.completed === false;
                });
            }
        },

        methods: {
            alertMe() {
                alert('haha! it works!');
            },

            increaseCounter() {
                this.counter++;
            },

            decreaseCounter() {
                this.counter--;
            }
        }
    }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>