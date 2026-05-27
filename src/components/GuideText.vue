<template>

<div
    v-if="guide"
    class="modal d-block"
    tabindex="-1"
>

    <div class="modal-dialog modal-lg">

        <div class="modal-content">

            <div class="modal-header">

                <h5 class="modal-title">
                    {{ guide.title }}
                </h5>

                <button
                    class="btn-close"
                    @click="$emit('close')"
                ></button>

            </div>

            <div class="modal-body">

                <div
                    v-for="(block, index) in guide.content"
                    :key="index"
                    class="mb-3"
                >

                    <img
                        v-if="block.type === 'image'"
                        :src="block.value"
                        class="img-fluid rounded"
                    >

                    <p v-if="block.type === 'text'">
                        {{ block.value }}
                    </p>

                </div>

            </div>

        </div>

    </div>

</div>

</template>

<script>
export default {

    props: {
        guide: Object
    }

}
</script>