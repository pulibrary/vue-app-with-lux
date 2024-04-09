# Vue 3 application with some lux components

This example application demonstrates importing
lux components into individual components in a Vue 3
application.  This allows vite to tree-shake
lux, packaging only the components it needs in the
bundle.

## Trying out this application in the browser

```
npm install
npm run dev
```

You can then see the application in your browser
at the port that vite provides.

## Confirming that vite can tree-shake lux

### Using vite bundle visualizer

1. To get the full size of the lux javascript: `ls -lh node_modules/lux-design-system/dist/lux-styleguidist.mjs`
    * As of April 9, 2024, it is about 495K
1. Run `npx vite-bundle-visualizer`.  This will open a report in your browse.
1. Use a mouse to hover over lux-styleguidist.mjs.
1. Note that after tree-shaking, only about 46% of the original
lux-styleguidist.mjs file gets included in the final bundle given
to the user for their browser.
1. If you add/remove components from HelloWorld.vue, then re-run
`npx vite-bundle-visualizer`, you should see that the percentage
of the original file that is rendered should change accordingly.


### Using ls and grep on the built package

1. Run `npm run build` to create a production build of this application.
1. Note that it says that the finished build is only 163.37 kB of javascript, smaller than the whole lux bundle.
1. Use grep to confirm that these components appear in the final bundled js:
    * LuxInputButton
    * LuxIconApproved
    * LuxIconBase
    * LuxInputRadio
    * LuxLibraryHeader
    * LuxMenuBar
1. Similarly, confirm that these components, which are not used
in our application, do not appear:
    * LuxIconHospital
    * LuxInputText
    * LuxLibraryFooter
