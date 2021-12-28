<template>
    <div class="box">
        <div class="mid">

            <h3>Your question is:</h3>

            <div class="viewer"> 
                <h4>{{ question }}</h4>
            </div>

            <hr/>

            <h3>Your answer is:</h3>

            <div class="viewer"> 
                <h4>{{ ans }}</h4>
            </div>

            <hr/>

            <div class="animate__animated animate__bounceIn animate__delay-1s">
                <button class="btn" @click="goBack">
                    Ask a new question
                </button>
            </div>

        </div>
        
    </div>

</template>


<script>
    export default {
        props: ["ans", "question"],
        mounted(){
            this.$emit("showAns")
        },
        methods:{
            goBack() {
                this.$emit("goto", 0);
                this.$emit("question", "");
            }
        }
    }

</script>


<style>

</style>