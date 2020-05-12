<template>
    <div>
 <div class="card student-list m-2 p-2">
            <h4 class="card-title">Students</h4>
            <div id="student-table">
                <table class="table">
                    <tr>
                        <th>Name</th>
                        <th>StarID</th>
                        <th>Present?</th>
                    </tr>
                                     <StudentRow 
                                     v-for="student in students"
                                      v-bind:key="student.name"
                                      v-bind:student="student"
                                      v-on:student-present="studentArrivedOrLeft"
                                     ></StudentRow>
                     </tr>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
import StudentRow from '@/components/StudentRow.vue'

export default {
    name: 'StudentTable',
    components: { StudentRow },
    
    props:{
        students: Array
    },
    methods: {
        studentArrivedOrLeft(student) {
            //todo emit message to parent
            this.$emit('student-present', student)
        }
    }
}
</script>

<style>

</style>