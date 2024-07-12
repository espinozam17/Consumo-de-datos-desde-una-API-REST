<template>
    <div id="scrollable" class="container chat mensaje">
        <div v-for="(mensaje, index) in mensajes" :key="index">
            <p :style="
                { textAlign: mensaje.id === usuarios[0].id.value ? 'left' : 'right' }">
                <small>{{ mensaje.nombreCompleto }}</small>
            </p>
            <p :style="{
                backgroundColor: mensaje.color,
                textAlign: mensaje.id === usuarios[0].id.value ? 'left' : 'right'}">
                {{ mensaje.texto }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "ChatUser",

    props: {
        mensajes: Array,
        usuarios: Array,
    }
}

</script>

<style scoped>


.mensaje {
  padding: 10px;
  border-radius: 5px;
  margin-bottom: 10px;
  max-width: 80%;
  word-wrap: break-word;
}

#scrollable {
    flex-grow: 2;
    max-height: 80vh;
    overflow-y: scroll;
    background-color: rgb(217, 230, 230);
}
</style>