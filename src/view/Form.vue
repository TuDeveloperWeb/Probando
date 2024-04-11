<template >
  <div class="container mx-5 my-5">
    <v-row>
      <v-col cols="12" md="6">
        <div class="card">
            <v-form>
              <div class="form-group">
                <label for="first-name">Subject:</label>
                <v-select
                  v-model="subject"
                  variant="underlined"
                  color="primary"
                  :items="['Geometria', 'Aritmetrica', 'Algebra', 'Trigonometria']"
                ></v-select>
              </div>
              <div class="form-group">
                <label for="first-name">Category:</label>
                <v-select
                  v-model="category"
                  :items="['UNI', 'San Marcos', 'Callao', 'Villareal']"
                  variant="underlined"
                  color="primary"
                ></v-select>
              </div>
              <div class="form-group">
                <label for="first-name">Level</label>
                <v-select
                  v-model="level"
                  :items="['Easy', 'Medium', 'Hard']"
                  variant="underlined"
                  color="primary"
                ></v-select>
              </div>
              <div class="form-group">
                <label for="first-name" >Question:</label>
                <div class="mt-3" >
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
                      'wordcount',
                    ],
                    toolbar:
                      'undo redo | blocks | bold italic | alignleft aligncenter alignright aligjjustify | outdent indent |tiny_mce_wiris_formulaEditor tiny_mce_wiris_formulaEditorChemistry',
                    external_plugins: {
                      tiny_mce_wiris:
                        '/node_modules/@wiris/mathtype-tinymce5/plugin.min.js',
                    },
                  }"
                />
                </div>
             
              </div>
            
              <v-btn color="primary" class="mt-5" @click="saveForm">
                Save
              </v-btn>
            </v-form>
        </div>
      </v-col>
      <v-col cols="12" md="6">
        <div class="Question">
            <h2 class="text-center text-primary mb-3">Question</h2>
            <p>{{texto}}</p>
        </div>

      </v-col>
    </v-row>
  </div>
</template>
<script setup>
import Editor from "@tinymce/tinymce-vue";
import { onMounted, ref } from "vue";

const texto = ref("");
const subject = ref("");
const category = ref("");
const level = ref("");


const saveForm = () => {
    
    const objForm = {
        'subject':subject.value,
        'texto':texto.value,
        'category':category.value,
        'level':level.value
    }

    console.log(objForm);
}



</script>
<style scoped>

    .card{
        border: 2px solid rgb(130, 139, 194);
        padding: 27px;
        border-radius: 10px;
        background-color: rgb(250, 253, 255);
    }

</style>