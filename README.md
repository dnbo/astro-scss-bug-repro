# Issue
`npm run dev` works fine while `npm run build` wont include the `/styles/app.css` in the output.

 ## Folder structure that causes the bug

If styles are arranged as below bug appears

```
/
├── public/
│   ├── robots.txt
│   └── favicon.ico
├── src/
│   ├── assets/
│   │   └── css
|   |   |   └── app.css
|   |   └── styles
|   |       └── app.scss        (this file @import's the ../css/app.css file)
```
The css is then imported in the `index.astro` like below

`<link rel="stylesheet" href={Astro.resolve('../assets/styles/app.css')} type="text/css">`
