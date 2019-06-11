<template>
    <div class="animation">
        <background>
            <div class="anim-container">
                <ball acid="ball"/>
                <mover acid="capital-move" x="300" y="300">
                    <spin speed="0.5" acid="capital-spin">
                        <heading :x="x1c" :y="y1c" size="1" acid="capital-heading">Ах у ели, ах у ёлки, ах у ели злые волки</heading>
                    </spin>
                </mover>
                <mover>test</mover>
                <heading  size="2" >Еду я по выбоине, из выбоины не выеду я</heading>
                <heading  size="3" >Улыбок тебе дед мокар!</heading>
                <heading  size="4" >Ох, у ямы холм с кулями, Выйду на холм - куль поправлю.</heading>
                <div class="box-container" ref=box1 >
                    <box id="redbox-1" size="200" color="blue" speed="3"/>
                </div>

            </div>
        </background>
    </div>
</template>

<script>
    
import box from './rotating_box.vue';
import background from './background.vue';
import heading from './heading.vue';
import spin from './spin.vue';
import ball from './ball.vue';
import mover from './mover.vue';
import { Linear, TweenMax } from 'gsap'
    
export default {
  name: 'scene_1',
  data: function() { return {  
      x1: -100,
      y1: 100
  }; },
  computed: {
      x1c: function(){
          return this.$data.x1;
      },
      y1c: function(){
          return this.$data.y1;
      }
  },
  components: {
      box, background, heading, spin, ball, mover
  },
  mounted() {
        const box1 = this.$refs.box1;
        //const timeline = new TimelineLite();
        var r = 150;
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
        TweenMax.to(this.$data, 2, {x: 100});
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
