## 此组件是根据 https://ext.dcloud.net.cn/plugin?id=1031 这个老哥的uni-app的图片裁剪工具进行的taro-vue的基础修改。后续不会更新，性能方面稍微有点卡，但是勉强都能用。文档请参考这位老哥的https://www.npmjs.com/package/gmy-img-cropper  ；uni-app链接
##### 如果有问题，请自行修改组件

### 可以直接下载。vue文件，在组件中引入即可。
#### 具体使用方式：

> <template>
    <view>
        <view >
            <button type="warn" @click="chooseImg" >选择图片</button>
        </view>
        <img-cropper
            ref="imgCropper"
            quality="0.5"
            cropperType="free"
            fileType="jpg"
            imgSrc=""
            @getImg="getImg"
        ></img-cropper>
    </view>
</template>

>  import imgCropper from '@/components/taro-vue-img-cropper/taro-vue-img-cropper.vue';
    export default {
        components:{
            imgCropper
        },
        data() {
            return {

            }
        },
        methods: {
            chooseImg:function(){
                // 调用实例的chooseImg方法，拉起图片选择界面，待图片选择完毕后直接进入图片截取界面
                this.$refs.gmyImgCropper.chooseImage();
            },
            // 点击完成时，返回截取图片的临时路径
            getImg:function(e){
                console.log("父页面拿到了图片",e);
                this.imgCropperShow = false;
            }
        }
    }
