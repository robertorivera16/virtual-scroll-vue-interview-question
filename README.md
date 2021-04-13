# Virtual Scroller in Vue.JS

## Description

Single file Vue component (.vue file) that will receive as a prop an array of strings called "items", the component will render a button that when clicked, will open a menu that will allow to scroll down the list of items you received as a prop.

   - The component will render the list in chunks of 20 items every time you scroll down to the end of the current list.
   - When the next 20 items render, the previous chunks is not be removed from the previuos rendered list.
   - When scrolled to the end of the list, the array should be rendered completely.
   - This components uses Vuetify, but without the vuetify component: 'v-virtual-scroll'.
   - The scroller do not use any external NPM library.

#### Preview

[Virtual Scroller Preview](VirtualScroller-Preview.mp4)

#### Benefits of Virtual Scrolling

[How Virtual Scrolling Works](https://medium.com/frontend-journeys/how-virtual-infinite-scrolling-works-239f7ee5aa58)
