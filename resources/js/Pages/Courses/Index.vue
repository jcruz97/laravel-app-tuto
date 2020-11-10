<template>
    <app-layout>
        <template #header>
            Courses available
        </template>
        <div class='py-7' v-for="course in this.courseList" v-bind:key="course.id">
            <div class='mx-7 bg-gray-200 rounded shadow p-3'>
                <div class='text-sm text-gray-600'>Mise en ligne par : {{course.user.name}}</div>
                 <div class='flex justify-between items-center'>
                     <div class='text-2xl'>{{course.title}}</div>
                     <div class="text-sm">{{ course.episodes_count}} épisodes</div>
                 </div>
                 <div class='text-sm text-gray-600'>{{course.description}}</div>
                 <a :href="'course/' + course.id" class='bg-indigo-500 text-white px-2 py-1 text-sm mt-3 rounded hover:bg-indigo-800
                 inline-block'>Voir cette formation</a>
            </div>
        </div>
    </app-layout>
</template>

<script>

import AppLayout from './../../Layouts/AppLayout';

export default {
    components : {
        AppLayout

    },

    data() {
        return {
            courseList: this.courses
        }
    },

    props : ['courses'],

    mounted() {
        console.log(this.courseList);
    }

}
</script>