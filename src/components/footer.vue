<template>

        <footer class="py-3 my-4 fixed-bottom">
            <ul class="nav justify-content-center border-bottom pb-3 mb-3">
                <v-pagination
                    v-model="page"
                    :pages="pages"
                    :range-size="1"
                    active-color="#DCEDFF"
                    @update:modelValue="$emit('updateHandler',page)"
                />
            </ul>
            <p class="text-center text-muted">© 2021 Company, Inc</p>
        </footer>

</template>

<script>
import VPagination from "@hennge/vue3-pagination";
import "@hennge/vue3-pagination/dist/vue3-pagination.css";

export default {
    name: "Footer",
    components: {
        VPagination,
    },
    props: {
        page: Number,
        pages: Number,
    },
    // methods: {
    //     updateHandler(page){
    //         this.$emit("updateHandler")
    //     }
    // },
}

</script>

<style scoped>
footer{
    position:static;
}
</style>