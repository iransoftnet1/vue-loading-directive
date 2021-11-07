# vue loading directive
Each tag is given a mask over its entire body area and your custom view or default views are displayed.
Fully expandable and changeable

Default view capabilities:
- size change
- color change
- loading type

How to use directive:
First define it in the main.js file 
```
import loading from '@/modules/loading/index.js'
Vue.use(loading.directive)
```

Then use this directive and give a bool value 

```
        <div v-loading="true">
          <router-view/>
        </div>
```
Send type to directive 
```
        <div v-loading:spinner="true">
          <router-view/>
        </div>
```
Send size to directive | 1 to 15 
```
        <div v-loading.size-5="true">
          <router-view/>
        </div>
```
To add a custom view, place it in the path below and impot it in the _loading.vue file
```
src/views/
```
