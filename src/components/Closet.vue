<template>
    <div>
        <div class="drop" :class="getClasses" @dragover.prevent="dragOver" @dragleave.prevent="dragLeave"
            @drop.prevent="drop($event)">

            <div class="img" v-for="img in imageSources" v-bind:key="img">
                <img :src="img" />
            </div>

            <h1 v-if="imageSources.length == 0 && !isDragging">Drop some images</h1>

            <!-- <div class="manual">
            <label for="uploadmyfile">
                <p>or pick from device</p>
            </label>
            <input type="file" id="uploadmyfile" :accept="'image/*'" multiple @change="requestUploadFile">
        </div> -->

        </div>
    </div>
</template>
  
  
  
<script>
export default {
    name: 'DropImages',
    data() {
        return {
            isDragging: false,
            imageSources: [],
        }
    },
    computed: {
        getClasses() {
            return { isDragging: this.isDragging }
        }
    },
    methods: {
        dragOver() {
            this.isDragging = true
        },
        dragLeave() {
            this.isDragging = false
        },
        async drop(e) {
            let files = [...e.dataTransfer.files]
            let images = files.filter(file => file.type.indexOf('image/') >= 0)
            let promises = []
            images.forEach(file => {
                promises.push(this.getBase64(file))
            })

            let sources = await Promise.all(promises)
            this.imageSources = this.imageSources.concat(sources)
            this.imageSources2 = this.imageSources2.concat(sources) // <---------------------
            this.isDragging = false
        },

        requestUploadFile() {
            var src = this.$el.querySelector('#uploadmyfile')
            this.drop({ dataTransfer: src })
        },

        getBase64(file) {
            const reader = new FileReader()
            return new Promise(resolve => {
                reader.onload = ev => {
                    resolve(ev.target.result)
                }
                reader.readAsDataURL(file)
            })
        }
    }
}
</script>
  
  
  
<style scoped>
.drop {
    width: 100%;
    height: 50%;
    background-color: #eee;
    border: 10px solid #eee;

    display: flex;
    align-items: center;
    justify-content: center;

    padding: 1rem;
    transition: background-color .2s ease-in-out;

    font-family: sans-serif;

    overflow: hidden;
    position: relative;
}



.isDragging {
    background-color: #999;
    border-color: #fff;
}

.img {
    padding: 1rem;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
}

img {
    width: 20%;
    height: 20%;
    object-fit: contain;
}

.manual {
    position: absolute;
    bottom: 0;
    width: 100%;
    text-align: center;
    font-size: .8rem;
    text-decoration: underline;
}

#uploadmyfile {
    display: none;
}
</style>
  