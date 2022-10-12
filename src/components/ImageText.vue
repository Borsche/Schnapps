<template>
    <div>
        <div v-if="left" class="row">
            <img src="./../assets/img.png"/>
            <div>
                <span>
                    Sie ergeben einen exellenten Whiskey welcher von der Zärtlichkeit und seinem Runden Charakter
                    definiert wird. Diese heben die feinen Nuancen und seine harmonisch balancierten aromatischen
                    Eigenschaften hervor.
                </span>
            </div>
        </div>
        <div v-if="!left" class="row">
            <div>
                <span>
                    Sie ergeben einen exellenten Whiskey welcher von der Zärtlichkeit und seinem Runden Charakter
                    definiert wird. Diese heben die feinen Nuancen und seine harmonisch balancierten aromatischen
                    Eigenschaften hervor.
                </span>
            </div>
            <img src="./../assets/img.png"/>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ImageText',
    props: ["left"]
}
</script>

<style scoped>
    .row {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .row img {
        max-width: 50%;
    }

    .row div {
        max-width: 50%;
        padding-left: 15px;
        padding-right: 15px;
    }

    .row div span {
    }
</style>