<script setup>
import { router } from "@inertiajs/vue3"


let nama=''
let nim=''

function buat() {
    router.post('/mahasiswa', {
        nama: nama,
        nim: nim
    })
}

</script>

<template>
    <div>
        <div class="join">
            <div>
                <div>
                    <input
                        class="input input-bordered join-item"
                        placeholder="Nama"
                        v-model="nama"
                    />
                </div>
            </div>
            <div>
                    <input
                        class="input input-bordered join-item"
                        placeholder="NIM"
                        v-model="nim"
                    />
                </div>
            <div class="indicator">
                <button @click="buat" class="btn join-item">Create</button>
            </div>
        </div>
    </div>
</template>
