<template>
    <v-container class="grey lighten-5">
        <v-btn v-on:click="stopCount()">Stop Count</v-btn>
        <v-btn v-on:click="startCount()">Start Count</v-btn>
        <v-row>
            <v-col class="col-lg-2"
                   v-for="textColor in textColors"
                   :key="textColor"
            >
                <span v-for="textStyle in textStyles"
                      :key="textStyle"
                      :class="[textColor, textStyle]"
                >
                    The counter = {{counter}}.<br/>
                </span>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: "HelloWorld",
        data: () => {
            return {
                textColors: [
                    "red--text", "pink--text", "purple--text", "deep-purple--text", "indigo--text", "blue--text",
                    "light-blue--text", "cyan--text", "teal--text", "green--text", "light-green--text", "lime--text",
                    "yellow--text", "amber--text", "orange--text", "brown--text", "blue-grey--text", "grey--text"

                ],
                textStyles: [
                    "text--darken-4", "text--darken-3", "text--darken-2", "text--darken-1", "text--lighten-1",
                    "text--lighten-2", "text--lighten-3", "text--lighten-4", "text--lighten-5", "text--accent-1",
                    "text--accent-2", "text--accent-3", "text--accent-4"
                ],
                counter: 0,
                counterTimer:null
            }
        },
        methods: {
            startCount: function () {
                this.counterTimer = setInterval(() => {
                    this.counter++
                }, 100)
            },
            stopCount:function(){
                clearInterval(this.counterTimer)
            }
        },
        mounted() {
            this.startCount()
        }
    }
</script>
