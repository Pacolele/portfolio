<script lang="ts">
    import Swiper from "swiper";
    import { register, type SwiperContainer } from "swiper/element/bundle";
    import { onMount } from "svelte";
    import "../css/home.css"

    //Init swiper
    register();

    let swiperEl: SwiperContainer;
    let swiperInstance: Swiper;
    let thumbnailEl: SwiperContainer;
    let thumbnailInstance: Swiper;

    onMount(() => {
        swiperEl = document.querySelector('.gallery');
        thumbnailEl = document.querySelector('.slider-thumbnail');
        if(swiperEl && thumbnailEl) {
            swiperInstance = swiperEl.swiper;
            thumbnailInstance = thumbnailEl.swiper;

            swiperInstance.on("slideChangeTransitionStart", function () {
                thumbnailInstance?.slideTo(swiperInstance?.activeIndex);
            });

            thumbnailInstance.on("slideChangeTransitionStart", function () {
                swiperInstance?.slideTo(thumbnailInstance?.activeIndex);
            })
        }

    })
</script>

<div class="content-container">

    <div class="swipers-container">
        <swiper-container
            class="gallery"
            slides-per-view="1"
            css-mode="true"
            navigation="true"
            pagination="true"
            thumbs-swiper=".slider-thumbnail"
        >
            
            <swiper-slide>
                <img alt="" src="/images/DSC_0027.JPG">
            </swiper-slide>
            <swiper-slide>
                <img alt="" src="/images/DSC_0056.JPG">
            </swiper-slide>
            <swiper-slide>
                <img alt="" src="/images/DSC_0655.JPG">
            </swiper-slide>
            
            <!-- extra -->
            <swiper-slide>
                <img alt="" src="/images/DSC_0027.JPG">
            </swiper-slide>
            <swiper-slide>
                <img alt="" src="/images/DSC_0056.JPG">
            </swiper-slide>
            <swiper-slide>
                <img alt="" src="/images/DSC_0655.JPG">
            </swiper-slide>
            
        
        </swiper-container>

        <swiper-container
            slides-per-view="3"
            class="slider-thumbnail"
            free-mode="true"
            direction="vertical"
            space-between="50"
            watch-slides-progres="true"
        >
            
            <swiper-slide class="thumbnail">
                <img alt="" src="/images/DSC_0027.JPG">
            </swiper-slide>
            <swiper-slide class="thumbnail">
                <img alt="" src="/images/DSC_0056.JPG">
            </swiper-slide>
            <swiper-slide class="thumbnail">
                <img alt="" src="/images/DSC_0655.JPG">
            </swiper-slide>

             <!-- extra -->
             <swiper-slide class="thumbnail">
                <p>Slide 4</p>
            </swiper-slide>
            <swiper-slide class="thumbnail">
                <p>Slide 5</p>
            </swiper-slide>
            <swiper-slide class="thumbnail">
                <p>Slide 6</p>
            </swiper-slide>
            
        
        </swiper-container>
    </div>
</div>


<style>
    @import 'swiper/swiper-bundle.css';
</style>


