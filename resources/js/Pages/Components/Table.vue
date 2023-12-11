<script setup>

import { router, Link } from '@inertiajs/vue3'

defineProps({ mahasiswas: Object });

function hapus(id){
    router.delete(`/mahasiswa/${id}`)
}

</script>

<template>
    <div class="overflow-x-auto">
        <table class="table">
            <!-- head -->
            <thead>
                <tr>
                    <th></th>
                    <th>Nama</th>
                    <th>NIM</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <!-- row -->
                <tr v-for="(item, index) in mahasiswas">
                    <th>{{ index+1 }}</th>
                    <td>{{ item.nama }}</td>
                    <td>{{ item.nim }}</td>
                    <td class="flex gap-2">
                        <button @click="hapus(item.id)" class="btn btn-outline btn-error btn-sm">
                            delete
                        </button>
                        <Link :href="`/mahasiswa/${item.id}/edit`" class="btn btn-outline btn-info btn-sm">
                            edit
                        </Link>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
