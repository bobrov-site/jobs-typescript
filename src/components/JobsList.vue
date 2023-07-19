<template>
    <div>
        <p>Ordered by {{ order }}</p>
        <ul>
            <li v-for="job in orderedJobs" :key="job.id" class="job">
                <h2>{{ job.title }} in {{ job.location }}</h2>
                <div class="salary">
                    <span>{{ job.salary }}₽</span>
                </div>
                <div class="description">
                    <p>
                        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quos quisquam, nisi exercitationem
                        voluptas voluptates perspiciatis molestias vero, corporis facilis voluptate cumque quibusdam?
                        Reiciendis blanditiis sunt culpa magni in cum! Nesciunt.
                    </p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import Job from '@/types/Job'
import OrderTerm from '@/types/OrderTerm';

export default defineComponent({
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>
        },
        order: {
            required: true,
            type: String as PropType<OrderTerm>
        }
    },
    setup(props) {
        const orderedJobs = computed(() => {
            return [...props.jobs].sort((a: Job, b: Job) => {
                return a[props.order] > b[props.order] ? 1 : -1
            })
        })
        return { orderedJobs }
    }
})
</script>

<style lang="css" scoped>
ul {
    list-style-type: none;
}

.job {
    padding: 1rem;
    background-color: #fff;
    margin-bottom: 2rem;
    border-radius: 15px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
    transition: box-shadow 0.3s ease;
}

.job:hover {
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2), 0 6px 20px rgba(0, 0, 0, 0.2);
    transform: translateY(-2px);
}

h2 {
    margin-top: 0;
}

.salary {
    color: green;
    font-weight: bold;
}

.description {
    margin-top: 1rem;
    color: #888;
}
</style>