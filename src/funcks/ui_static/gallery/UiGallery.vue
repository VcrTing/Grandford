<template>
    <div>
        <div class="fx-l fx-t" :class="{ 'pro-gallery': mode == 'CROSS' }">
            <div class="w-88">
                <div class="pr">
                    <img class="img" :src="src">
                </div>
            </div>
            <div class="w-12">
                <div class="w-100 pro-gry-ul pt_s">
                    <div class="" v-for="(v, i) in gallery" :key="i">
                        <img class="img" :src="v.src">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        mode: {
            type: String,
            default: 'CROSS'
        }
    },
    data() {
        return { 
            gallery: [
                { src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp4.itc.cn%2Fq_70%2Fimages03%2F20210827%2F2395168e45a447c9a6c24ab6e7182f61.jpeg&refer=http%3A%2F%2Fp4.itc.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1651309142&t=772053b4fbcb85c49efef5302dac0858' },
                { src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp4.itc.cn%2Fq_70%2Fimages03%2F20210827%2F2395168e45a447c9a6c24ab6e7182f61.jpeg&refer=http%3A%2F%2Fp4.itc.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1651309142&t=772053b4fbcb85c49efef5302dac0858' },
                { src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp4.itc.cn%2Fq_70%2Fimages03%2F20210827%2F2395168e45a447c9a6c24ab6e7182f61.jpeg&refer=http%3A%2F%2Fp4.itc.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1651309142&t=772053b4fbcb85c49efef5302dac0858' },
                { src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp4.itc.cn%2Fq_70%2Fimages03%2F20210827%2F2395168e45a447c9a6c24ab6e7182f61.jpeg&refer=http%3A%2F%2Fp4.itc.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1651309142&t=772053b4fbcb85c49efef5302dac0858' }
            ],
            src: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp4.itc.cn%2Fq_70%2Fimages03%2F20210827%2F2395168e45a447c9a6c24ab6e7182f61.jpeg&refer=http%3A%2F%2Fp4.itc.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1651309142&t=772053b4fbcb85c49efef5302dac0858' }
    }
}
</script>

<style lang="sass">
.pro-gry-ul
    div
        cursor: pointer
        transition: all .362s ease-in
        &:hover 
            transform: scale(1.08)
        img
            border-radius: 0.15em

.pro-gallery
    flex-wrap: wrap
    & > div
        width: 100% !important
    .pro-gry-ul
        width: 100%
        margin-left: -6px !important
        div
            width: 25% 
            padding: 0px 6px !important
            display: inline-block 

</style>