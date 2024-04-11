# Initial Setup Commands (For Reference To Setup Other Projects With Vite)

1. Create a project with vite using the command `npm create vite@latest`. For consistency with the course, `npm create vite@4` was used. Choose `React` -> `JavaScript`.
1. Install dependencies with `npm i` in the root folder.
1. Note that the file structure is slightly different in comparison with `create-react-app`:
   -  all files are now the `.jsx` extension instead of `.js`.
   -  The entrypoint is `\src\main.jsx` instead of `index.js`, and `index.html` is outside of the `\src\` folder.
1. (If using a different CSS file) Delete the .css files in `\src\` and remove the reference to any css files in `\src\main.jsx`.
1. Overwrite everything in `\src\App.jsx` with a fresh component:

   ```
        function App() {
           return <div>App Stuff Goes Here</div>;
        }

        export default App;
   ```

1. Run the app with `npm run dev`.
1. The instructions seem to differ with what happened when creating this app. The instructions said ESLint needs to be configured for each new vite project:

   1. Run `npm install eslint vite-plugin-eslint eslint-config-react-app --save-dev`
   1. Create `.eslintrc.json` and create an object:
      ```
      {
          "extends":"react-app"
      }
      ```
   1. In `vite.config.js` add an import `import eslint from "vite-plugin-eslint";` and add `eslint()` to the plugins array. The entire config file should now look like this:

      ```
      import { defineConfig } from 'vite';
      import react from '@vitejs/plugin-react';
      import eslint from "vite-plugin-eslint";

      // https://vitejs.dev/config/
      export default defineConfig({
          plugins: [react(), eslint()],
      })
      ```

   However, a file `eslintrc.cjs` was automatically created when running `npm create vite@4`, and ESLint already seemed to work with testing, **so these steps of the instructions were ignored** (perhaps this is an update to the ESLint plugin, a difference between Windows/Mac, or else an update to vite itself).

# React Router

1. Installing React Router:
   -  For consistency with the course, version 6 was used: `npm install react-router-dom@6`. Future project should just use `npm install react-router-dom` for the latest version.
