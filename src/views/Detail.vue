<template>
    <ion-card color="light">
        <ion-card-header>
            <ion-card-title>
                <ion-label>{{ post.title }}</ion-label>
            </ion-card-title>
        </ion-card-header>
        <ion-card-content>
            <ion-img :src="image"></ion-img>
            {{ post.selftext }}
            <ion-button color="tertiary" expand="full" @click="$router.go(-1)">Go Back</ion-button>
        </ion-card-content>
    </ion-card>
</template>

<script>
export default {
    props: ['post'],
    data() {
        return {
            image: ''
        }
    },
    mounted() {
        this.image = this.post.preview.images[0].source.url.replace('&amp;', '&');
    }
}
</script>
