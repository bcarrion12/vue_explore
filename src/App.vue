<template>
  <div>
    <div class="control-section file-overview">
      <div class="sample-container">
        <ejs-filemanager
          id="overview_file"
          :ajaxSettings="ajaxSettings"
          :view="view"
        >
        </ejs-filemanager>
      </div>
    </div>
  </div>
</template>
<style>
@import "../../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-icons/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-navigations/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-layouts/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-grids/styles/material.css";
@import "../../node_modules/@syncfusion/ej2-vue-filemanager/styles/material.css";
.file-overview .sample-container {
  margin: 10px 10px 10px 10px;
}
</style>
<script>
import Vue from "vue";
import {
  FileManagerPlugin,
  NavigationPane,
  Toolbar,
  DetailsView,
  FileManagerComponent,
} from "@syncfusion/ej2-vue-filemanager";

Vue.use(FileManagerPlugin);
/**
 * File Manager full functionalities sample
 */
let hostUrl = "https://ej2-aspcore-service.azurewebsites.net/";
export default Vue.extend({
  data: function () {
    return {
      ajaxSettings: {
        url: hostUrl + "api/FileManager/FileOperations",
        getImageUrl: hostUrl + "api/FileManager/GetImage",
        uploadUrl: hostUrl + "api/FileManager/Upload",
        downloadUrl: hostUrl + "api/FileManager/Download",
      },
      view: "Details",
    };
  },
  provide: {
    filemanager: [NavigationPane, DetailsView, Toolbar],
  },
});
</script>