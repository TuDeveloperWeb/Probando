<script setup>
import Editor from '@tinymce/tinymce-vue'
import { onMounted, ref } from 'vue';

const texto = ref('')

</script>

<template>
 <editor
    v-model="texto"
    api-key="ap3mk9aojiqe683mauz9krbijkqyp6tiz2q4d7vdjdm289b3"
    :init="{
        draggable_modal: true,
        plugins: [
            'image', 
            'media', 
            'a11ychecker',
            'advcode',
            'template',
            'table ',
            'autolink',
            'autoresize',
            'autosave',
            'casechange',
            'charmap',
            'checklist',
            'code',
            'codesample',
            'directionality',
            'emoticons',
            'export',
            'formatpainter',
            'fullscreen',
            'help',
            'importcss',
            'insertdatetime',
            'link',
            'linkchecker',
            'lists',
            'mediaembed',
            'mentions',
            'nonbreaking',
            'pagebreak',
            'pageembed',
            'permanentpen',
            'powerpaste',
            'preview',
            'quickbars',
            'save',
            'searchreplace',
            'table',
            'template',
            'tinydrive',
            'tinymcespellchecker',
            'visualblocks',
            'visualchars',
            'wordcount'
        ],
        toolbar: 'undo redo | blocks | bold italic | alignleft aligncenter alignright aligjjustify | outdent indent |tiny_mce_wiris_formulaEditor tiny_mce_wiris_formulaEditorChemistry',
        external_plugins : {
            'tiny_mce_wiris' : '/node_modules/@wiris/mathtype-tinymce5/plugin.min.js'
        },
    }"
  />
   <div>
    <span v-text="texto">

</span>
   </div>
</template>