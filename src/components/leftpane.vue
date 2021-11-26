<template>
    <div class="container py-5 mb-5 d-flex ">
        <h1>Data</h1><h1 class="text-success">Hub</h1>
    </div>
    <ul class="list-group align-text-center ">
        <li class="hover list-group-item d-flex justify-content-between bg-dark text-light align-items-center py-5"
        >
        <div class="ms-2 me-auto">
            <span></span>
            <div class="fw-bold ms-4">OverView</div>
        </div>
        </li>
        <li class="hover list-group-item d-flex justify-content-between bg-dark text-light align-items-center py-5"
        >
        <div class="ms-2 me-auto">
            <span></span>
            <div class="fw-bold ms-4">Regional</div>
        </div>
        </li>
        <li class="hover list-group-item d-flex justify-content-between bg-dark text-light align-items-center py-5"
        >
        <div class="ms-2 me-auto">
            <span></span>
            <div class="fw-bold ms-4">Districts</div>
        </div>
        </li>
    </ul>
</template>

<script>
export default {
    name: "leftpane",
    data() {
        return {
            hover: false,
            
        }
    },
    methods: {
      
    },
}

</script>

<style scoped>

.hover:hover{
    border-color: antiquewhite;
    border-top-width: 0px !important;
    border-right: 0px !important;
    border-bottom: 0px !important;
    border-left-width: 15px;
}
</style>