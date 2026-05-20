<template>

<div class="container py-4">

    <div class="hero">

        <h1 class="text-center text-md-start text-primary">
            HOW TO Guides
        </h1>

        <p class="d-none d-md-block">
            Перевод оффициальных гайдов по продукции Mr Hobby.
        </p>

    </div>

    <h4 class="mb-4">
        Всего: {{ totalGuides }}
    </h4>

    <div class="row">

        <div
            class="col-12 col-md-6 col-lg-4 mb-4"
            v-for="(guide, index) in guides"
            :key="index"
        >

            <GuideCard
                :guide="guide"
                @open-guide="openGuide"
            />

        </div>

    </div>

    <GuideText
        :guide="selectedGuide"
        @close="selectedGuide = null"
    />

</div>

</template>

<script>

import GuideCard from './components/GuideCard.vue'
import GuideText from './components/GuideText.vue'

export default {

    components: {
        GuideCard,
        GuideText
    },

    data() {
        return {

            selectedGuide: null,

            guides: [

                {
                    title: 'Решение проблем с аэрографом.',
                    
                    image: 'https://www.mr-hobby.com/uploads/articles/01K4PGDWPJ2RWY4N7FV9KSKEX5.png',
                    text: 'Решение различных неурядиц в формате Q&A.'
                },

                {
                  title: "Грунтовки.",
                  image: "https://www.mr-hobby.com/uploads/articles/richeditor/9fN3OBBGQlOJj0zJRmSUGuZQQnGOrglJejzHTms8.jpg",
                  text: "Все про грунтовки.",

                }

                

            ]

        }
    },

    computed: {

        totalGuides() {
            return this.guides.length
        }

    },

    methods: {

        openGuide(guide) {
            this.selectedGuide = guide
        }

    }

}
</script>