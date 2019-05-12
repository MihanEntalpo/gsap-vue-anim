<template>
    <div class="animation">
        <background />
        <div class="animation-container">
            <heading text="Капитал" x="100" y="100" size="1" />
            <heading text="Том 1. Серия 1." x="100" y="200" size="2" />
            <heading text="Глава: Товар" x="100" y="300" size="3" />
            <heading text="Природа стоимости" x="100" y="400" size="4" />
            <heading text="Товарный фетишизм" x="100" y="500" size="5" />
            <div class="box-container" ref=box1 >
                <box id="redbox-1" size="200" color="blue" speed="3"/>
            </div>
        </div>
    </div>
</template>

<script>
    
import box from './rotating_box.vue';
import background from './background.vue';
import heading from './heading.vue';
import { Linear, TweenMax } from 'gsap'
    
export default {
  name: 'scene_1',
  props: {  
  },
  components: {
      box, background, heading
  },
  mounted() {
        const box1 = this.$refs.box1;
        //const timeline = new TimelineLite();
        var r = 300;
        var xc = parseInt(window.innerWidth / 2);
        var yc = parseInt(window.innerHeight / 2);
        TweenMax.set(box1, {x: xc , y: yc - r});
        TweenMax.to(box1, 5, {bezier:{type:'thru', values:
                        [
                            /*p1*/{x:xc, y:yc - r},
                            /*p2*/{x:xc + r, y:yc},
                            /*p3*/{x:xc, y:yc + r},
                            /*p4*/{x:xc - r, y:yc},
                                  {x:xc, y:yc - r}
                        ]
                }, ease:Linear.easeNone, repeat: -1 });
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h1{
        color:blue;
    }
    .box-container
    {
        position: absolute;
    }
    body{
        overflow: hidden;
    }
</style>
