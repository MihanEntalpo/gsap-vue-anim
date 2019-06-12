<template>
    <div class="animation">
        <background>
            <div class="anim-container">
                <layer acid="ball-layer">
                    <mover acid="ball-mover" x="100" y="100">
                        <ball acid="ball"/>
                    </mover>
                </layer>
                <layer acid="experiments-layer" opacity="0">
                    <mover acid="capital-move" x="200" y="500">
                        <spin speed="0.02" acid="capital-spin">
                            <heading  size="1" acid="capital-heading">Ах у ели, ах у ёлки, ах у ели злые волки</heading>
                        </spin>
                    </mover>
                    <mover :x="test.x1" :y="test.y1" acid="test-mover"><heading size=1 acid="test-heading">test</heading></mover>
                    <heading  size="2" >Еду я по выбоине, из выбоины не выеду я</heading>
                    <heading  size="3" >Улыбок тебе дед мокар!</heading>
                    <heading  size="4" >Ох, у ямы холм с кулями, Выйду на холм - куль поправлю.</heading>
                    <div class="box-container" ref=box1 >
                        <box id="redbox-1" size="200" color="blue" speed="3"/>
                    </div>
                </layer>
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
import layer from './layer.vue';
import { Linear, TweenMax } from 'gsap'
    
export default {
  name: 'scene_1',
  data: function() { 
    return {  
        
        test: {
            x1: 200,
            y1: 200
        }
    }; 
  },
  props: {      
  },
  computed: {
     
  },
  components: {
      box, background, heading, spin, ball, mover, layer
  },
  mounted() {
        
        //const timeline = new TimelineLite();
        var r = 150;
        var xc = parseInt(window.innerWidth / 2);
        var yc = parseInt(window.innerHeight / 2);
        
        
        const box1 = this.$refs.box1;
        if (box1)
        {
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
        
        TweenMax.to(this.test, 5, {x1:500, y1:500})
        
       
        
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
    [acid=test-heading]
    {
        color:orange;
        text-shadow: 0px 2px 2px rgba(150, 150, 150, 1);
    }
</style>
