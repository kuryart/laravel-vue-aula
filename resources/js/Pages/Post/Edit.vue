<template>
    <Head title="Dashboard" />

    <AppLayout title="Posts">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Edit
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <form @submit.prevent="submit">
                            <div>
                                <label for="title">Title</label>
                                <input
                                    type="text"
                                    v-model="form.title"
                                    class="w-full px-4 py-2 mt-2 border rounded-md focus:outline-none focus:ring-1 focus:ring-blue-600"
                                />
                            </div>
                            <div>
                                <label for="title">Description</label>
                                <textarea
                                    name="description"
                                    type="text"
                                    v-model="form.description"
                                    class="w-full px-4 py-2 mt-2 border rounded-md focus:outline-none focus:ring-1 focus:ring-blue-600"
                                >
                                </textarea>
                            </div>

                            <!-- submit -->
                            <div class="flex items-center mt-4">
                                <button
                                    class="px-6 py-2 text-white bg-gray-900 rounded"
                                >
                                    Save
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </AppLayout>
</template>

<script>
import AppLayout from '@/Layouts/AppLayout.vue';
import { Head } from "@inertiajs/inertia-vue3";
import { useForm } from "@inertiajs/inertia-vue3";
export default {
    components: {
        Head,
    },
    setup(props) {
        const form = useForm({
            title: props.post.title,
            description: props.post.description,
        });

        return { form };
    },
    props: {
        post: Object,
    },
    methods: {
        submit() {
            this.form.put(route("posts.update", this.post.id));
        },
    },
};
</script>
