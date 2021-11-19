# Vue Medias Upload Component
Vue component that provides drag and drop images & videos upload with preview.

![demo](./demo.gif)

## Features

* Upload files by Drag & Drop
* Upload files by clicking on the upload icon
* Add Medias
* Delete Medias
* Append Medias
* Remove all Medias

## Example

[DEMO](https://vueupload.yudax.dev)

## Install

1. install the package:

    ```bash
        npm i vue-upload-drop-medias --save
    ```

2. import it in your project

   .vue file:
   ```javascript
        <script>
            import UploadMedias from "vue-upload-drop-medias"
            ...
            export default {
                    components: {
                        UploadMedias,
                    },
            ...
        </script>
   ```

3. add component in template
   ```html
        <template>
        ...
            <UploadMedias />
        ...
        </template>

   ```

4. for Nuxt support
  .nuxt.config:
    ```javascript
    build: {
      transpile: ['vue-upload-drop-medias']
    }
    ```

## Events

### <b>@changed</b>
Fired when new medias are added or deleted it always returns uploaded files

Template:

```html
        <UploadMedias @changed="handleMedias"/>
```

Script:

```javascript
    ...
        methods:{
            handleMedias(files){
                console.log(files)
                /*
                  [
                    {
                        "name": "Screenshot from 2021-02-23 12-36-33.png",
                        "size": 319775,
                        "type": "image/png",
                        "lastModified": 1614080193596
                        ...
                    },
                    ...
                    ]
                 */
            }
        }
    ...
```



## Props

### <b>Accept Video</b>
Type: `Boolean`

Required: `false`

default: `false`

```html
    <!-- the user can upload also videos -->
    <UploadMedias :acceptVideo="true" />
```

### <b>max</b>
Type: `Number`

Required: `false`

default: `null`

```html
    <!-- the user can upload up to 5 medias-->
    <UploadMedias :max="5"/>
```

### <b>maxError</b>
Type: `String`

Required: `false`

default: `Maximum files is`

```html
    <!-- the error message that the user sees when the uploaded medias greater that the max medias required-->
    <UploadMedias maxError="Max files exceed"/>
```

### <b>uploadMsg</b>
Type: `String`

Required: `false`

default: `Click to upload or drop your images here`

```html
    <!-- the message that the user see to upload the medias -->
    <UploadMedias uploadMsg="upload product images/videos"/>
```

### <b>fileError</b>
Type: `String`

Required: `false`

default: `Unsupported file type`

```html
    <!-- the message that the user see when the uploaded file is not an image or a video -->
    <UploadMedias fileError="images and videos files only accepted"/>
```

### <b>clearAll</b>
Type: `String`

Required: `false`

default: `clear All`

```html
    <!-- the name of the remove all medias button -->
    <UploadMedias clearAll="remove all medias" />
```