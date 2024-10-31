<script setup lang="ts">
import { onUnmounted, onMounted, ref, defineProps } from 'vue';
import * as Ayame from '@open-ayame/ayame-web-sdk/dist/ayame.min.js';

console.log(Ayame);


const options = Ayame.defaultOptions;

let videoCodec;
let conn;
let reConnect = true;
const remoteVideoElement = ref(null);
const videoCodecElement = ref(null);


const props = defineProps({
  signalingUrl: String,
  roomId: String,
  clientId: String
});

options.clientId = props.clientId ? props.clientId : options.clientId;
options.video.direction = 'recvonly';
options.audio.direction = 'recvonly';

const disconnect = () => {
    reConnect = false;
    if (conn) {
        conn.disconnect();
    }
}

const startConn = async () => {
    reConnect = true;
    options.video.codec = videoCodec;
    conn = Ayame.connection(props.signalingUrl, props.roomId, options, true);
    await conn.connect(null);
    conn.on('open', ({ authzMetadata }) => console.log(authzMetadata));
    conn.on('disconnect', async (e) => {
        console.log(e);
        remoteVideoElement.value.srcObject = null;
        if (reConnect) {
            await conn.connect(null);
        }
    });
    conn.on('addstream', (e) => {
        remoteVideoElement.value.srcObject = e.stream;
    });
};

onMounted(() => {
    startConn();
});

onUnmounted(() => {
    if (conn) {
        disconnect(); 
    }
});
</script>

<template>
    <div style="height: 100%;width: 100%;display: flex;">
        <video id="remote-video" autoplay playsinline controls></video>
    </div>
</template>

<style scoped lang="scss">
/* 你的样式代码 */
</style>