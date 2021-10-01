See `package.json` for scripts.

**Develop** using `npm start` to boot React app on localhost:3000/ and `npm startdb` to boot a local database on localhost:3001/
 - they have to be on separate ports. In package.json see the `proxy` property, which tells React to redirect any API requests made locally to the database on port 3001
 - `routes.json` routes data in `db.json` to the expected URL in production. You can therefore make a request in Production and copy the result into `db.json`, setup a route in `routes.json` so that you can mock the API request and develop locally.

**Build** using `npm build`. This outputs files to the `/build` folder. 
 - Upload `#.chunk.js` and `main.id.chunk.js` as Web Files in the Dynamics Portal
 - Copy entire `/build/index.html` file into your Dynamics 365 Portals HTML file. Ensure `<script>` tags point correctly to URL of Web Files created above
 - Note `<div id="root"`> in `index.html` - this is where compiled React app is placed in your Portal HTML