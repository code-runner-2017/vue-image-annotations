<template>
  <div>
    <img :src="src" @load="init" ref="img">
  </div>
</template>

<script>
import 'annotorious';
import 'annotorious/css/theme-dark/annotorious-dark.css';
import 'annotorious-selector-pack/src/fancy_box_selector.js';
// var anno;

export default {
  name: 'v-annotated-img',
  components: {

    },
  data () {
    return {

    }
  },
  props: {
    src: String
  },
  mounted() {
    this.onMounted();
  },
  methods: {
    init() {
      window.anno.makeAnnotatable(this.$refs.img);

      var myAnnotation = {
        src: this.$props.src,
        /** The annotation text **/
        text : 'My annotation, lorem ipsum',

        /** The annotation shape **/
        shapes : [{
          /** The shape type **/
          type : 'rect',

          /** The shape geometry (relative coordinates) **/
          geometry : { x : 0.1, y: 0.1, width : 0.2, height: 0.2 }
        }]
      };

      window.anno.addAnnotation(myAnnotation);
      window.anno.showAnnotations();
    },
    onMounted() {
      // https://github.com/annotorious/annotorious/wiki/JavaScript-API#annogetannotationsopt_item_url
      anno.addPlugin('FancyBoxSelector', { activate: true });
      anno.addHandler('onAnnotationCreated', this.onAnnotationCreated);
      anno.addHandler('onAnnotationRemoved', this.onAnnotationRemoved);
      anno.addHandler('onAnnotationUpdated', this.onAnnotationUpdated);
    },
    onAnnotationCreated(annotation) {
      console.log("onAnnotationCreated: " + annotation.text);

      if (annotation.text.trim() == '') {
        anno.removeAnnotation(annotation)
      }
    },
    onAnnotationRemoved(annotation) {
      console.log("onAnnotationRemoved: " + annotation.text);
    },
    onAnnotationUpdated(annotation) {
      console.log("onAnnotationUpdated: " + annotation.text);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import '~annotorious/css/theme-dark/annotorious-dark.css';

</style>
