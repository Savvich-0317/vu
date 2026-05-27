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
import g1 from './assets/image.psd.jpg';
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

        content: [

        {
            type: 'text',
            value: 'WIP'
        }

        

    ]
        
    },

    {
        title: "Грунтовки.",

        image: "https://www.mr-hobby.com/uploads/articles/richeditor/9fN3OBBGQlOJj0zJRmSUGuZQQnGOrglJejzHTms8.jpg",

        content: [

        {
            type: 'image',
            value: g1
        },

        {
            type: 'text',
            value: 'Про цифры на грунтовках.\n Они обозначают величину распыляемых частиц.\n Чем больше число - гладче итоговая поверхность.'
        },

        {
            type: 'image',
            value: 'https://www.mr-hobby.com/uploads/articles/richeditor/pWNlscNXaF8Wum1QEJ3x8jotFGrod0BkZbpmVhWb.jpg'
        },

        {
            type: 'text',
            value: 'Помимо стандартных грунтовок на сольвентовом растворителе(Mr finishing surfaser, base) Существуют более безопасные аналоги на спиртовом растворителе (aqueous).\nТакже существует водная серия базовых слоев acrysion которую можно разбавлять водой.'
        },
        {
            type: 'image',
            value: 'https://www.mr-hobby.com/uploads/articles/richeditor/u3bWxAwRcAdtKsO3pjBgjmZuWsrS1zAZEseZNgW4.jpg'
        },
        {
            type: 'text',
            value: 'Собвственно сама причина по которой нужна грунтовка это наличие адгезивного связующего вещества с пластиком. На сольвенте это вещество приваривается к пластику создавая эту адгезию.'
        },


    ]
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