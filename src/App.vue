<script setup>
import{ref,reactive} from 'vue'
const findex=ref(0)
const currentIndex=ref()

const fullImage = ref('https://th-thumbnailer.cdn-si-edu.com/XJFrDNlNhvtv1uH-U6FKdBJ_U2U=/1000x750/filters:no_upscale()/https://tf-cmsv2-smithsonianmag-media.s3.amazonaws.com/filer/04/8e/048ed839-a581-48af-a0ae-fac6fec00948/gettyimages-168346757_web.jpg')
const images = [
  {
    thumb: "https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxfHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://th-thumbnailer.cdn-si-edu.com/XJFrDNlNhvtv1uH-U6FKdBJ_U2U=/1000x750/filters:no_upscale()/https://tf-cmsv2-smithsonianmag-media.s3.amazonaws.com/filer/04/8e/048ed839-a581-48af-a0ae-fac6fec00948/gettyimages-168346757_web.jpg"
  },
  {
    thumb: "https://images.unsplash.com/photo-1682695794816-7b9da18ed470?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDZ8fHxlbnwwfHx8fHw%3D&auto=format&fit=crop&w=300&q=60",
    full: "https://c4.wallpaperflare.com/wallpaper/431/451/684/the-most-beautiful-picture-of-nature-wallpaper-preview.jpg"
  },
  {
    thumb: "https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE4fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://images.pexels.com/photos/268533/pexels-photo-268533.jpeg?cs=srgb&dl=pexels-pixabay-268533.jpg&fm=jpg"
  },
  {
    thumb: "https://plus.unsplash.com/premium_photo-1666963323736-5ee1c16ef19d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=300&q=60",
    full: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_1280.jpg"
  }
]

let length=images.length-1
console.log(length)

const changeFullImage=(image)=>{
  fullImage.value=image.full
}
function next(){
 findex.value = findex.value+1
 if(findex.value>length){
  findex.value=0
 }
 
 fullImage.value=images[findex.value].full
}
function previous(){
 findex.value = findex.value-1
 if(findex.value<0){
  findex.value=length-1
 }
 fullImage.value=images[findex.value].full
}


</script>

<template>
  
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Image carousel</h1>
     
          <img  :src="images" key="index" alt="">
            <div class="flex item-center" >   

              <button @click="previous()" class="px-2 py-1 bg-blue-500 text-white  hover:bg-blue-600 focus:outline-none focus:bg-blue-600" >&lt;</button>
                <img class="cursor-pointer w-72 h-52" :src="fullImage" alt="">
               
                <button @click="next()" class="px-2 py-1 bg-blue-500 text-white  hover:bg-blue-600 focus:outline-none focus:bg-blue-600">></button>
                
            </div>
           
        
      
      

            
        
    </section>
</template>

<style scoped></style>