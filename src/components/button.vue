<template>
    <button class="feel-btn" :style="style" :type="type" :class="btnClass" @click="handleClick">
        <i v-if="icon"></i>
        <slot></slot>
    </button>
</template>
<script>
    export default {
        name: "feel-button",
        props: {
            icon: {
                type: String,
                default: "",
            },
            type: {
                type: String,
                default: "button",
            },
            disabled: {
                type: Boolean,
                default: false,
            },
            circle:{
                type:Boolean,
                default:false
            },
            large:{
                type:Boolean,
                default:false
            },
            small:{
                type:Boolean,
                default:false
            },
            color:{
                type:String,
                default:""
            },
            bgColor:{
                type:String,
                default:""
            }
        },
        computed: {
            btnClass() {
                return {
                    "disabled-btn": this.disabled,
                    "circle-btn": this.circle,
                    "large-btn": this.large,
                    "small-btn": this.small
                };
            },
            style(){
                return {
                    "color": this.color,
                    "background-color": this.bgColor
                }
            }
        },
        methods: {
            handleClick(e) {
                if (this.disabled) {
                    e.preventDefault();
                    e.stopPropagation();
                }
                this.$emit("click", e);
            },
        },
    };
</script>
<style scoped lang="less">
    @green:green;
    @white:#fff;
    @width:100px;
    @height:40px;
    .feel-btn {
        display: block;
        width: 100px;
        height: 40px;
        color: @white;
        font-size: 14px;
        outline: none;
        user-select: none;
        cursor: pointer;
        border: none;
        background-color: @green;
        box-sizing: border-box;
        -webkit-tap-highlight-color: transparent
    }
    .disabled-btn {
        color: @green;
        cursor: none;
        background-color: #ccc;
    }
    .circle-btn {
        border-radius: 25px;
    }
    .large-btn {
        font-size: 16px;
        width: 120px;
        height: 50px;
    }
    .small-btn {
        font-size: 12px;
        width: 80px;
        height: 30px;
    }
</style>