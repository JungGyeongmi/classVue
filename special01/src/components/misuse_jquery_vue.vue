<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script src="https://code.jquery.com/jquery-3.6.0.min.js"
    integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
<template>
    <div>
        {{ msg }}
        <button id="btn">시작</button>
        <p id="pEl"></p>
    </div>
</template>
<script>
   export default {
        data() {
            return {
                msg: 'Hello Vue.js'
            }
        },
        created() {
            $('#btn').click(function (e) {
                e.preventDefault();
                $('#pE1').text('jQuery')
            });
        }
    }
</script>