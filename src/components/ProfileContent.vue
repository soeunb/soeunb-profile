<template>
  <main>
    <div class="container">
      <div class="gallery">
        <div v-for="(item, index) in photos" :key="index" class="gallery-item">
          <div @click="imgClick(item)" style="cursor:pointer;">
            <img :src="item.thumbnail" class="gallery-image"/>
            <div class="gallery-item-info">
              <ul>
                <li class="gallery-item-comments"><span class="visually-hidden">Comments:</span><i class="fas fa-comment" aria-hidden="true"></i> {{ item.description }}</li>
              </ul>
            </div>
          </div>
          <ProfileDetail v-if="item.show" @close="item.show = false">
            <div slot="body">
              <img :src="item.thumbnail" class="gallery-image-2" :class="`img-index--${index}`"/>
            </div>
            <h3 slot="body">body바꾸기</h3>
            <h3 slot="footer">footer바꾸기</h3>
          </ProfileDetail>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import ProfileDetail from './ProfileDetail.vue'

export default {
  props: {
    items: { type: Array, default: () => [] }
  },
  data() {
    return {
      //showModal: false,
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
      //this.showModal = !this.showModal;
      item.show = true
    }
  },
  components: {
    ProfileDetail: ProfileDetail
  }
}
</script>

<style scoped>
.gallery-image-2 {
  width: 30%;
  height: 30%;
}
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

.gallery-item-info li {
    display: inline-block;
    font-size: 1.7rem;
    font-weight: 600;
}

.fa-clone,
.fa-comment {
    transform: rotateY(180deg);
}

.gallery-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
</style>
