<template>
    <el-container class="building">
        <el-contain class="title" style="height:20%;margin-top: 10vh;">
            El Psy Congroo !
        </el-contain>
        <el-container>
            <el-container style="height:70%;margin-top: 15vh;display: flex;flex-direction: row;" v-for="(item,index) in Digits" :key="index" class="center-container">
                <el-image class="digits" :src="getDigitPath(item)" fit="contain"/>
            </el-container>
        </el-container>
        <el-container style="height:20%"/>
    </el-container>
</template>

<script>
import zeroPath from '@/assets/digits/0.png';
import onePath from '@/assets/digits/1.png';
import twoPath from '@/assets/digits/2.png';
import threePath from '@/assets/digits/3.png';
import fourPath from '@/assets/digits/4.png';
import fivePath from '@/assets/digits/5.png';
import sixPath from '@/assets/digits/6.png';
import sevenPath from '@/assets/digits/7.png';
import eightPath from '@/assets/digits/8.png';
import ninePath from '@/assets/digits/9.png';
import backGroundImage from '@/assets/background.jpg';
export default {
    name:"SteinsCounter",
    props:{
        DigitsString:String,
    },
    data(){
        return{
            Digits: [],
            digitPaths: [
                zeroPath, onePath, twoPath, threePath, fourPath,
                fivePath, sixPath, sevenPath, eightPath, ninePath
            ],
            backGroundImage: backGroundImage,
        }
    },
    methods: {
        splitDigits() {
            const digits = this.DigitsString.replace(/:/g, ''); // 去除时间字符串中的冒号
            // 将每个数字字符存储在数组中
            this.Digits = digits.split('').map(Number);
            console.log(this.Digits)
        },
        getDigitPath(digit) {
            return this.digitPaths[digit];
        }
    },
    created() {
        this.splitDigits();
    },
}
</script>

<style scoped>
.building{
    background-color:#000000 ;
    left:0px;
    top:0px;
    width:100vw;			
    height:100vh;
    position: fixed;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.center-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.digits{
    width: 10vw;
    height: 20vh;
}
.title{
    font-family: STXingkai;
    height: 15vh;
    font-size: 5em;
    color: #f0f3f4;
}
</style>