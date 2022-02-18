<template>
    <app-layout title="Notas">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Módulo de Notas
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="md:grid md:grid-cols-3 md:gap-6">
                    <div class="md:col-span-1">
                        <div class="px-4 sm:px0">
                            <h3 class="text-lg text-gray-900">
                                Listado de notas
                            </h3>
                            <p class="text-sm text-gray-600">
                                Toma el registro correcto y ejecuta cualquier
                                funcion (ver, editar o eliminar)
                            </p>
                        </div>
                    </div>
                    <div class="md:col-span-2 mt-5 md:mt-0">
                        <div class="shadow bg-white md:rounded-md p-4">
                            <table>
                                <tr v-for="note in notes" :key="note.id">
                                    <td class="border px-4 py-2">
                                        {{ note.excerpt }}
                                    </td>
                                    <td class="px-4 py-2">
                                        <inertia-link :href="route('notes.show', note.id)">
                                            Ver
                                        </inertia-link>
                                    </td>
                                    <td class="px-4 py-2">
                                        <inertia-link :href="route('notes.edit', note.id)">
                                            Editar
                                        </inertia-link>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
import { defineComponent } from "vue";
import AppLayout from "@/Layouts/AppLayout.vue";
import Welcome from "@/Jetstream/Welcome.vue";

export default defineComponent({
    components: {
        AppLayout,
        Welcome,
    },

    props:{
        notes: Array
    }
});
</script>
