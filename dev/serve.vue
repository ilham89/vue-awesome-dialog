<script>
import { defineComponent } from "vue-demi";
import VueAwesomeDialog from "@/vue-awesome-dialog.vue";

export default defineComponent({
    name: "ServeDev",
    components: {
        VueAwesomeDialog,
    },
});
</script>

<template>
    <div id="app">
        <vue-awesome-dialog />
    </div>
</template>
