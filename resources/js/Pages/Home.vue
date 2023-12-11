<script setup>
import Table from './Components/Table.vue';
import Create from './Components/Create.vue';

defineProps({ mahasiswas: Object })

</script>

<template>
    <div class="min-h-screen">
        <div class="flex flex-col">
            <div class="mx-8 mt-8">
                <Create/>
            </div>
            <div class="card mx-8 shadow-xl">
                <Table :mahasiswas="mahasiswas"/>
            </div>
        </div>
    </div>
</template>
