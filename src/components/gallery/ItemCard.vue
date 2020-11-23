<template>
    <div class="item-card" @mouseover="mouseOver" @mouseleave="mouseLeave">
        <img :src="item.download_url" style="border-radius: 10px;">
        <v-fade-transition>
            <div class="cover" v-show="isMouseOver">
                <div>
                    <v-text-field solo></v-text-field>
                </div>
                <div></div>
            </div>
        </v-fade-transition>
    </div>
</template>

<script>
    export default {
        name:'ItemCard',
        props:["item"],
        data(){
            return{
                isMouseOver:false,
                title:category
            };
        },
        methods:{
            mouseOver(){
                this.isMouseOver = true;
            },
            mouseLeave(){
                this.isMouseLeave = false;
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>