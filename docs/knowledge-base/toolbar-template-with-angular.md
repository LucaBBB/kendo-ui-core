---
title: Create Custom ToolBar Templates
page_title: Create Custom ToolBar Templates - Kendo UI for jQuery Data Grid
description: "Learn how to create a custom ToolBar template in an AngularJS application using the Kendo UI Grid for jQuery."
previous_url: /kendo-mvc/controls/data-management/grid/how-to/AngularJS/toolbar-template-with-angular, /controls/data-management/grid/how-to/AngularJS/toolbar-template-with-angular
slug: howto_create_custom_toolbar_templates_grid
tags: create, custom, toolbar, template, grid, angularjs
component: grid
type: how-to
res_type: kb
---

## Environment

<table>
 <tr>
  <td>Product</td>
  <td>Progress® Kendo UI® Grid for jQuery</td> 
 </tr>
 <tr>
  <td>Operating System</td>
  <td>All</td>
 </tr>
 <tr>
  <td>Browser</td>
  <td>All</td>
 </tr>
 <tr>
  <td>Browser Version</td>
  <td>All</td>
 </tr>
</table>

## Description

How can I create a custom ToolBar template in an AngularJS application using the Kendo UI Grid for jQuery?

## Solution

The following example demonstrates how to create a custom ToolBar template in AngularJS applications.


```dojo
<div id="example" ng-app="KendoDemos">
  <div ng-controller="MyCtrl">

      <script id="template" type="text/x-kendo-template">
          {{ gridName }}
          <a class="k-button" href="\#" ng-click="toolbarClick()">Command</a>
      </script>

      <div kendo-grid
         k-toolbar="toolbarTemplate"
         k-columns="[{ title: 'foo' , field: 'foo' },
                    { title: 'bar' , field: 'bar' }]"
         k-data-source="data">
      </div>
  </div>
</div>

<script>
    function MyCtrl($scope) {
        $scope.data = new kendo.data.DataSource({ data: [{foo: "foo", bar: "bar"}] });
        $scope.gridName = "My Grid";
        $scope.toolbarTemplate = $("#template").html();
        $scope.toolbarClick = function() { console.log("click"); }
    }

    angular.module("KendoDemos", ["kendo.directives"])
           .controller("MyCtrl", MyCtrl);
</script>
```

## See Also

* [JavaScript API Reference of the Data Grid](/api/javascript/ui/grid)
* [Bind to Telerik Backend Services]({% slug howto_bindto_telerik_backend_services_grid %})
* [Change Languages Dynamically]({% slug howto_dynamic_language_change %})
* [Create Custom Editors]({% slug howto_create_custom_editors_grid %})
* [Create Custom Edit Buttons]({% slug howto_create_custom_edit_buttons_grid %})
* [Use AngularJS in Popup Editor Templates]({% slug howto_use_angularin_popup_editor_templates_grid %})
* [Use Resize Columns from a Button]({% slug howto_resize_columnsfrom_abutton_grid %})

For more runnable examples on the Kendo UI Grid, browse its [**How To** documentation folder]({% slug howto_adjust_row_heights_template_locked_columns_grid %}).
