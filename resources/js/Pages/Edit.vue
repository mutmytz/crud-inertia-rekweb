<script setup>
import { router } from "@inertiajs/vue3";

const props = defineProps({ mahasiswa: Object });

let nama = props.mahasiswa.nama;
let nim = props.mahasiswa.nim;

function edit() {
    router.put(`/mahasiswa/${props.mahasiswa.id}`, {
        nama: nama,
        nim: nim
    })
}

</script>

<template>
    <div class="flex justify-center h-screen items-center">
        <div class="card w-content p-8 shadow-xl">
            <label
                class="form-control w-full max-w-xs items-center justify-center"
            >
                <div class="label self-start">
                    <span class="label-text">Nama</span>
                </div>
                <input
                    type="text"
                    placeholder="Type here"
                    class="input input-bordered w-full"
                    v-model="nama"
                />
                <div class="label self-start">
                    <span class="label-text-alt">NIM</span>
                </div>
                <input
                    type="text"
                    placeholder="Type here"
                    class="input input-bordered"
                    v-model="nim"
                />
                <button @click="edit" class="btn btn-outline btn-info btn-sm mt-8">
                    update
                </button>
            </label>
        </div>
    </div>
</template>
