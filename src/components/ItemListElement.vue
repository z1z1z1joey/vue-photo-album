<template>
<div class="photo-item">
  <div class="photo" :style="imgShow">
  </div>
  <h3>{{title}}</h3>
  <p>{{description}}</p>
  <div class="photo-btn-container" v-if="isLogin">
    <button @click="handleShow">Show</button>
    <button @click="handleEdit">Edit</button>
    <button @click="handleDelete">Destory</button>
  </div>
</div>
</template>

<script>
export default {
  props: {
    isLogin: {
      type: Boolean,
      default: false
    },
    id: {
      type: Number,
      default: 1
    },
    title: {
      type: String,
      default: "title"
    },
    description: {
      type: String,
      default:
        "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi, exercitationem!"
    },
    url: {
      type: String,
      default: "http://via.placeholder.com/200x200"
    }
  },
  methods: {
    handleShow: function() {
      this.$router.push("/photos/" + this.id);
      console.log("show");
    },
    handleEdit: function() {
      this.$router.push("/photos/edit/" + this.id);
      console.log("edit");
    },
    handleDelete: function() {
      console.log("destroy");
    }
  },
  computed: {
    imgShow: function() {
      return {
        background: "url(" + this.url + ") no-repeat center",
        backgroundSize: "cover"
      };
    }
  }
};
</script>

<style scoped>
/* skip */
</style>