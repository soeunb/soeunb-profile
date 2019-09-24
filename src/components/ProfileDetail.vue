<template>
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper" @click.self="$emit('close')">
        <div class="app__phone">
          <div class="feed">
            <div class="instagram-post">
              <div class="header headroom">
                <div class="level-left">
                  <img src="../assets/imgs/profile.gif" class="modal-header-img"/>
                  <div class="user">
                    <span class="username">soeun.b</span>
                    <button class="modal-default-button" @click="$emit('close')">
                      ✖
                    </button>
                  </div>
                </div>
              </div>
              <slot name="modal-img"></slot>
              <div class="content">
                <div class="content-title">
                  <slot name="modal-tit"></slot>
                </div>
                <p class="caption"><span class="username">soeun.b</span>&nbsp;<slot name="modal-des"></slot></p>
              </div>
            </div>
          </div> 
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default{

}
</script>

<style>
body {
  height: 100%;
  margin: 0;
  font-family: 'Roboto', sans-serif;
  color: #4a4a4a;
  font-weight: 400;
  line-height: 1.5;
}

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.app__phone {
  background-color: white;
  height: 620px;
  width: 350px;
  margin: 0px auto;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
  transition: all .3s ease;
  font-family: Helvetica, Arial, sans-serif;
  overflow: hidden;
}

.feed {
  height: 100%;
  margin-right: -17px;
  overflow-y: scroll;
  overflow-x: hidden;
}

.instagram-post {
  padding-top: 50px;
  padding: 5px 0;
}

.instagram-post .header {
  height: 40px;
  border-bottom: 1px solid #fff;
  margin: 7.5px 10px;
}

.instagram-post .header .modal-header-img {
  /*display: inline-block;*/
  width: 10%;
  height: 10%;
  border-radius: 99px;
  float: left;
}

.user {
  float: left;
  padding-top: 7px;
}

.instagram-post .user {
  padding-left: 7px;
  font-size: 14px;
  color: #262626;
}

.username {
  font-weight: bold;
}

.modal-default-button {
  margin-left: 210px;
  background-color: transparent;
  background-image: none;
  border-color: transparent;
  border: none;
  cursor: pointer;
}

.instagram-post .image-container {
  height: 350px;
}

.instagram-post .content {
  margin: 7.5px 10px;
  color: #4a4a4a;
  font-size: 14px;
  font-weight: 400;
  line-height: 1.7;
  word-break:normal;
}

.instagram-post .content-title {
  font-size: 14px;
  font-weight: bold;
}

.instagram-post .caption {
  font-size: 13px;
  margin-top: 5px;
}

.instagram-post .caption-bottom {
  /*color:#5D5D5D;*/
  font-size:12px;
}

/* Media Query */

@media screen and (max-width: 40rem) {
  .feed {
    margin-right: -6px;
  }
}
</style>
