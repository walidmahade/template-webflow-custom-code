# Webflow custom code template


---

### 1. Watch for changes and recompile the code:
```bash
npm run watch
# or
yarn watch
# or
pnpm watch
```

### 2. Run a dev server:
To use the compiled code from dist in a webflow website.
```bash
npm run preview
# or
yarn preview
# or
pnpm preview
```

### 3. Add the following link to the head of your webflow website:
```html
<link rel="stylesheet" href="http://localhost:4173/assets/index.css">
```


### 4. Add the following script to the bottom of your webflow website:
By bottom we mean before the closing body tag.
```html
<script src="http://localhost:4173/assets/index.js"></script>
```

---

#### Special note 1: 
The port number here was taken from a M1 Mac device. If you are using windows or linux, the port number might be different. You can find the port number in the terminal where you ran the `npm run preview` (described in step 2) command.

#### Special note 2:
Vite by default removes all the `console.log` statements from the code. If you want to keep them, you can do so in one of the following ways:
```javascript
const { log } = console;
// or
window.console.log('Hello world');
```

---

# Production deployment
You can use `vercel` or `cloudflare` pages to deploy the code. After deployment, you can use the preview url to link to your `dist`
folder assets.

---

#### Special note 3:
In our `.gitignore`, we are not ignoring the `dist` folder. Which contains the compiled code.
So you can ignore the build step in your CI/CD pipeline. Since the dist folder is already present in the repository.
You dont need to run the build step in the CI/CD pipeline.

