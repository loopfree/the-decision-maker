<template>
    <div class = "container">
        <component
            :is="screens[position]"
            :question = "question"
            :ans = "ans"
            @goto = "jumpPage"
            @question = "passingQuestion"
            @showAns = "getAns"
        />
    </div>

</template>


<script>
    import inputDecision from "./components/inputDecision.vue"
    import outputDecision from "./components/outputDecision.vue"

    export default {
        components:{
            inputDecision,
            outputDecision
        },
        data(){
            return {
                list: [
                    "Yes",
                    "No",
                    "Maybe"
                ],
                screens: ["inputDecision","outputDecision"],
                position: 0,
                question: "",
                ans: ""
            }
        },
        methods:{
            jumpPage(position) {
                this.position = position
            },
            passingQuestion(question) {
                this.question = question
            },

            createAns() {
                let rand = this.list[Math.floor(Math.random()*this.list.length)];
                this.ans = rand;
            },
            getAns() {
                this.createAns()
            }
        }
    }

</script>


<style>
    @import "./assets/sass/style.css";
</style>