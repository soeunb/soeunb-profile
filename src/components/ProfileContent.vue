<template> 
    <div class="container">
      <div class="gallery">
        <div v-for="(item, index) in photos" :key="index" class="gallery-item">
          <div @click="imgClick(item)" style="cursor:pointer;">
            <img :src="item.thumbnail" class="gallery-image"/>
            <div class="gallery-item-info">
              <div class="gallery-item-comments">{{ item.period }}</div>
            </div>
          </div>
          <ProfileDetail v-if="item.show" @close="hideModal(item)">
            <div slot="modal-img">
              <img :src="item.thumbnail" class="image-container" :class="`img-index--${index}`"/>
            </div>
            <span slot="modal-tit"><img src="../assets/imgs/heart.png" class="heart" />&nbsp;{{ item.title }}</span>
            <span v-html="item.description" slot="modal-des"></span>
          </ProfileDetail>
        </div>
      </div>
    </div>
</template>

<script>
import ProfileDetail from './ProfileDetail.vue'

export default {
  props: {
    items: { type: Array, default: () => [] }
  },
  data() {
    return {
      photos: {}
    }
  },
  created() {
    this.photos = this.items.map(item => {
      return { ...item, show: false }
    })
  },
  methods: {
    imgClick(item) {
      item.show = true
      document.body.classList.add("modal-open")
    },
    hideModal(item) {
      item.show = false
      document.body.classList.remove("modal-open")
    }
  },
  components: {
    ProfileDetail: ProfileDetail
  }
}
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
  margin: -1rem -1rem;
  padding-bottom: 3rem;
}

.gallery-item {
  position: relative;
  flex: 1 0 22rem;
  margin: 1rem;
  color: #fff;
  cursor: pointer;
}

.gallery-item:hover .gallery-item-info,
.gallery-item:focus .gallery-item-info {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.3);
}

.gallery-item-info {
  display: none;
}

.gallery-item-info .gallery-item-comments {
  display: inline-block;
  font-size: 1.7rem;
  font-weight: 600;
}

.gallery-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.heart {
  cursor: pointer;
  width: 5%;
  height: 5%;
  float: left;
}
</style>
