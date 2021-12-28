<template>

    <div class="box">
        <div class="mid">

            <h1> Ask a question </h1>
            
            <div class="mb-3">
                <input
                    name = "question"
                    type = "text"
                    class = "form-control"
                    id = "question"
                    v-model = "question"
                    placeholder = "Start with is/am/are"
                />

                <!--
                {{question}}
                -->

                <button
                    v-if = "question"
                    class = "btn"
                    @click = "goToAns"
                >
                    Get Answer
                </button>

            </div>

        </div>

    </div>

</template>


<script>
    // Var to check user input
    var am = "am";
    var Am = "Am";

    var is = "is";
    var Is = "Is";

    var are = "are";
    var Are = "Are";

    // function to get the first word from a string
    function getFirstWord(str) {
        let spaceIndex = str.indexOf(" ");
        return spaceIndex === -1 ? str : str.substr(0, spaceIndex);
    }

    export default {
        data() {
            return {
                question: ""
            }
        },
        methods: {
            goToAns(e) {
                e.preventDefault();

                var check = getFirstWord(this.question);

                if (check.includes(am) || check.includes(Am)){
                    this.$emit("goto",1);
                    this.$emit("question", this.question);
                }

                else if (check.includes(is) || check.includes(Is)){
                    this.$emit("goto",1);
                    this.$emit("question", this.question);
                }
                
                else if (check.includes(are) || check.includes(Are)){
                    this.$emit("goto",1);
                    this.$emit("question", this.question);
                }
                
            }
        }
    }

</script>


<style>

</style>