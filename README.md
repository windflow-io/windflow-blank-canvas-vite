# windflow-blank-canvas-vite
A blank setup that you can just pull in order to create a brand new windflow website that you can modify and/or add to and deploy to Netlify (or any other JAMStack SPA compatible host).

## Pre-Deployment Notes
The windflow-magic-toolbar dependency is a dependency created as:
```json
    {
        "dependencies": {
            "@windflow/windflow-magic-toolbar": "file:../windflow-magic-toolbar",
            "vue": "^3.0.5"
        }
    }
```
that needs to be replaced with ("lastest" not tested)
```json
    {
        "dependencies": {
            "@windflow/windflow-magic-toolbar": "latest",
            "vue": "^3.0.5"
        }
    }
```
Simply `npm run build` windflow-magic-toolbar dependency project. Vite HMR will pick up the changes to `dist/windflow-magic-toolbar.es.js`  
