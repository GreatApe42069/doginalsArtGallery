# 🐶 Đoginals Art Gallery

Welcome to the **Doginals Art Gallery**, an interactive, fully on-chain 3D art gallery built using Doginals (inscriptions on the Dogecoin blockchain). This project showcases a metaverse-style gallery where users can explore inscribed artwork, textures, fonts, and scripts in a 3D environment. The gallery is designed to be a template, allowing you to customize it with your own Doginal inscriptions, text, lighting, and scaling to create your own unique on-chain gallery.

This README provides step-by-step instructions for setting up and customizing your own gallery using this repository as a template.

## Table of Contents

1. Project Overview
2. Prerequisites
3. How It Works
4. Inscribing Your Assets and HTML Files
5. Customizing the Gallery
   - Editable Sections in ApestractArtGalleryMetaverse.html
   - Editable Sections in ApestractArtGallerySplash.html
   - Non-Editable Sections
6. Deploying Your Gallery
7. Usage Instructions
8. Contributing
9. License

## Project Overview

The Doginals Art Gallery is a fully on-chain, interactive 3D art gallery powered by Dogecoin inscriptions (Doginals). All assets, including images, textures, fonts, cursors, and scripts, are inscribed on the Dogecoin blockchain and referenced using their inscription IDs. The gallery is built using HTML, JavaScript, and Three.js, creating an immersive metaverse experience where users can:

- Navigate the 3D space using WASD or arrow keys (desktop) or on-screen controls (mobile).
- View inscribed artwork with clickable links to marketplaces.
- Customize text, lighting, and scaling to suit their needs.

This repository serves as a template for anyone looking to create their own on-chain 3D art gallery using their Doginal inscriptions. The project consists of two main files:

- **ApestractArtGallerySplash.html** (Example that is referred to as splash.html): The landing page with introductory text, artwork preview, and a link to enter the 3D gallery.
- **ApestractArtGalleryMetaverse.html** (Example that is referred to as metaverse.html): The core 3D gallery file containing the Three.js scene, assets, and interactive elements.

## Prerequisites

To use this project as a template, you’ll need:

- A Dogecoin wallet with access to a Doginal inscription service (e.g., doginals.js, Doggy.Market, DogeLabs or similar platforms).
- Basic knowledge of HTML, CSS, JavaScript, and Three.js for customization.
- A web server or hosting platform to deploy your gallery (e.g., IPFS, a traditional web server, or a Doginal-compatible hosting service).
- Your own Doginal inscriptions for images, textures, fonts, cursors, and other assets.

## How It Works

The gallery is built using inscribed assets stored on the Dogecoin blockchain. Instead of hosting files locally or on a centralized server, all assets (images, textures, fonts, cursors, scripts, and even the HTML files themselves) are referenced using their Doginal inscription IDs. For example:

- Images are displayed on gallery walls using inscription IDs.
- Textures for the gallery’s walls, floor, and ceiling are also loaded from inscriptions.
- Custom fonts and cursors are also inscribed assets....Such On-chain

When all assets and HTML files are inscribed, the gallery becomes a fully decentralized, on-chain experience that loads directly from the blockchain. Users access the gallery by visiting the inscription URL of the splash.html (e.g., `/content/SPLASH_INSCRIPTION_ID`).

## Inscribing Your Assets and HTML Files

Before customizing the gallery, you need to inscribe your assets on the Dogecoin blockchain. Importantly, the HTML files themselves must also be inscribed, and the order matters because splash.html references the inscription ID of metaverse.html.

1. **Prepare Your Assets**:

   - **Images**: Create or select the artwork you want to display in the gallery (e.g., PNG, JPEG). This includes gallery artworks and any preview image for the splash page.
   - **Textures**: Prepare textures for the gallery’s walls, floor, and ceiling (e.g., PNG or JPEG files).
   - **Fonts**: Use a custom TrueType font (`.ttf`) for text in the gallery.
   - **Cursors**: Design a custom cursor image (e.g., .ani , .cur , .png)  
   - **Scripts**: If you need additional custom scripts, ensure they are compatible with your gallery setup.

2. **Inscribe Assets**:

   - Use a Doginal inscription service like DogeLabs or another platform to inscribe your assets on the Dogecoin blockchain.
   - Each asset will receive a unique inscription ID (e.g., `0798bf75ab07fcdf153c13fc07ef381916a010ebe5d5729564aef3dd0aac4a54i0`).
   - ***Save the inscription IDs for each asset, as you’ll need to reference them in the code***

3. **Inscribe the HTML Files (Order Matters)**:

   - **First, inscribe metaverse.html**: After editing it with your asset inscription IDs (see Customizing the Gallery), inscribe the metaverse.html file. Note down its inscription ID (e.g., `YOUR_METAVERSE_INSCRIPTION_ID`).
   - **Then, inscribe splash.html**: Edit splash.html to include the metaverse.html inscription ID (as a link), then inscribe splash.html last. This ensures the splash page can correctly point to the 3D gallery.
   - **Important**: splash.html must be inscribed last because it relies on the inscription ID of metaverse.html. Attempting to inscribe splash.html first will result in an invalid link.

4. **Organize Inscription IDs**:

   - Keep a list of your inscription IDs for images, textures, fonts, cursors, and the metaverse.html Inscribed InscriptionID. You’ll need to update the code with these IDs (see Customizing the Gallery).

**Important**: All assets and HTML files must be inscribed before final deployment, as the code relies on these inscriptions to load content.

## Customizing the Gallery

To use this project as a template, you’ll need to edit specific sections of the two HTML files to include your own inscription IDs, text, lighting settings, and scaling. Below are the editable and non-editable sections for each file.

### Editable Sections in ApestractArtGalleryMetaverse.html

This file contains the 3D gallery logic. Modify the following:

1. **Custom Cursor**: Update the cursor to use your inscribed cursor image.

   ```css
   body {
       cursor: url('/content/YOUR_CURSOR_INSCRIPTION_ID'), auto; /* Replace with your cursor inscription ID */
   }
   ```

2. **Custom Font**: Update the font to use your inscribed TrueType font.

   ```css
   @font-face {
       font-family: 'CustomFont';
       src: url('/content/YOUR_FONT_INSCRIPTION_ID') format('truetype'); /* Replace with your font inscription ID */
   }
   ```

3. **Textures**: Update the textures for the ceiling, walls, and floor to use your inscribed texture images.

   ```javascript
   const ceilingTexture = textureLoader.load('/content/YOUR_CEILING_TEXTURE_INSCRIPTION_ID'); /* Replace with your ceiling texture ID */
   const wallTexture = textureLoader.load('/content/YOUR_WALL_TEXTURE_INSCRIPTION_ID'); /* Replace with your wall texture ID */
   const floorTexture = textureLoader.load('/content/YOUR_FLOOR_TEXTURE_INSCRIPTION_ID'); /* Replace with your floor texture ID */
   ```

4. **Gallery Title and Modal Text**: Update the gallery title and modal text to reflect your project’s branding and instructions.

   ```html
   <title>YOUR_GALLERY_TITLE</title>
   <div id="modal">
       <div id="modalContent">
           <p>YOUR_GALLERY_NAME</p>
           <p>YOUR_CUSTOM_INSTRUCTIONS_LINE_1</p>
           <p>YOUR_CUSTOM_INSTRUCTIONS_LINE_2</p>
           <p>YOUR_CUSTOM_INSTRUCTIONS_LINE_3</p>
           <p>YOUR_CUSTOM_INSTRUCTIONS_LINE_4</p>
           <p>YOUR_CUSTOM_INSTRUCTIONS_LINE_5</p>
           <button id="okButton">OK</button>
       </div>
   </div>
   ```

   - Replace `YOUR_GALLERY_TITLE` with your gallery’s title (e.g., "My Doginal Gallery").
   - Replace `YOUR_GALLERY_NAME` with the name displayed in the modal.
   - Customize the instruction lines (`YOUR_CUSTOM_INSTRUCTIONS_LINE_X`) to provide guidance for your users (e.g., navigation instructions, marketplace links, etc.).

5. **Inscription IDs for Artwork**: Update the array of inscription IDs to display your artwork in the gallery.

   ```javascript
   const inscriptionIds = [
       "YOUR_INSCRIPTION_ID_1",
       "YOUR_INSCRIPTION_ID_2",
       "YOUR_INSCRIPTION_ID_3",
       "YOUR_INSCRIPTION_ID_4",
       "YOUR_INSCRIPTION_ID_5",
       "YOUR_INSCRIPTION_ID_6",
       "YOUR_INSCRIPTION_ID_7",
       "YOUR_INSCRIPTION_ID_8"
   ];
   ```

   Replace `YOUR_INSCRIPTION_ID_X` with the inscription IDs of your artwork images. You can add or remove IDs to match the number of artworks you want to display.

6. **Lighting**: Adjust the lighting settings in the Three.js scene to suit your gallery’s aesthetic.

   ```javascript
   const ambientLight = new THREE.AmbientLight(0xffffff, 0.5); // Adjust color and intensity
   const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8); // Adjust color and intensity
   directionalLight.position.set(0, 10, 10); // Adjust position
   scene.add(ambientLight, directionalLight);
   ```

   - Modify the color (e.g., `0xffffff` for white) and intensity (e.g., `0.5` or `0.8`) to change the lighting.
   - Adjust the `position` of the directional light to control the angle of illumination.

7. **Scaling and Positioning**: Adjust the scale and position of objects (e.g., artwork, walls) in the 3D scene.

   ```javascript
   const artwork = new THREE.Mesh(geometry, material);
   artwork.scale.set(1, 1, 1); // Adjust scale (x, y, z)
   artwork.position.set(0, 1, -5); // Adjust position (x, y, z)
   scene.add(artwork);
   ```

   - Modify `scale.set(x, y, z)` to resize artwork or other objects.
   - Modify `position.set(x, y, z)` to reposition objects in the 3D space.

### Editable Sections in ApestractArtGallerySplash.html

This file is the landing page. Modify the following:

1. **Gallery Title**: Update the main heading.

   ```html
   <h1>YOUR_GALLERY_TITLE</h1> <!-- Replace with your gallery title, e.g., "My Custom Art Gallery" -->
   ```

2. **Preview Artwork**: Update the image or artwork preview (if present, using Markdown or HTML syntax for links).

   ```html
   ![Alt text](/content/YOUR_PREVIEW_ARTWORK_INSCRIPTION_ID) <!-- Replace with your preview artwork inscription ID -->
   ```

   Or if it's a link:

   ```html
   <a href="/content/YOUR_PREVIEW_ARTWORK_INSCRIPTION_ID"></a> <!-- Adjust as needed -->
   ```

3. **Introductory Text**: Customize the descriptive paragraph.

   ```html
   <p>YOUR_CUSTOM_TEXT_HERE</p> <!-- Replace with your own description, e.g., "Explore 100 masterpieces with hidden secrets..." -->
   ```

4. **Link to Metaverse**: Update the link to point to your inscribed metaverse.html.

   ```html
   <a href="/content/YOUR_METAVERSE_INSCRIPTION_ID">Enter the Gallery</a> <!-- Replace with the inscription ID of metaverse.html -->
   ```

   This is crucial, as it connects the splash page to the 3D gallery.

### Non-Editable Sections

**Do NOT edit the following section** in metaverse.html, as it is critical for the gallery to function:

```html
<script src="/content/f8d6d9594ff93cb4190cfa81d877b81b59b0d2acd975685fdd12efd0452bd190i0"></script>
```

This script is an inscribed asset required for the gallery’s core functionality. Changing or removing it will break the gallery.

Avoid editing core Three.js setup, event listeners, or rendering logic unless you are experienced, as it may disrupt the 3D experience.

## Deploying Your Gallery

Once you’ve customized and inscribed the files, your gallery is ready to be accessed via the blockchain:

1. **Test Locally**:

   - Use a local web server (e.g., `python -m http.server` or a tool like XAMPP) to test your gallery.
   - Ensure all inscription IDs are valid and assets load correctly.

2. **Access via Inscription URLs**:

   - The entry point is the inscription URL of splash.html (e.g., `https://your-doginal-explorer/content/SPLASH_INSCRIPTION_ID`).
   - For fully decentralized hosting, use an IPFS gateway if you've pinned the inscriptions, or a Doginal-compatible script, client, or platform like Doggy.market, or DogeLabs.

3. **Verify Functionality**:

   - Test the link from splash.html to metaverse.html.
   - Confirm navigation (WASD/arrow keys on desktop, on-screen controls on mobile).
   - Ensure artwork loads and links to the marketplace correctly.
   - Check that textures, fonts, and cursors load as expected.
   - Check Scale of textures and lighting positions

### Real Example of a Functional Gallery:
🔗 Click Me

 <a href="https://wonky-ord.dogeord.io/content/d2f3a4a2945d3fbaa62664f4eea6634fb9828ec2285fcddcec5d86764f5b433bi0"><img src="./images/hero_0.8.jpg" alt="Greatape42069E" width="500px;"></a>

## Usage Instructions

Once deployed, users can interact with your gallery as follows:

- Start at the splash page for introduction and entry.
- Click the link to enter the 3D metaverse gallery.
- **Desktop**: Use WASD or arrow keys to navigate, click and drag to look around, and click on artwork to view in the marketplace.
- **Mobile**: Follow on-screen instructions for navigation.
- **Refresh**: Press refresh to load new images (if applicable).
- **Back**: Use the back button to return to the previous view.
- **Modal**: A modal with instructions appears on load in the metaverse; click "OK" to dismiss.

Customize the modal text and splash text (see Customizing the Gallery) to provide specific instructions for your users.


## License

This project is licensed under the Creative Commons Legal Code

CC0 1.0 Universal

See the [LICENSE](LICENSE.md) file for details.


# 🛠 Contributing

If you'd like to contribute or donate to this project, please donate in Dogecoin. For active contributors its as easy as opening issues, and or creating pull requests.

Contributions are welcome! If you have ideas for improving the gallery or adding new features, please:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add your feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

Please ensure all contributions respect the on-chain nature of the project and use Doginal inscriptions for assets.....Much Immutable So On-chain

This software is Open-source, Decentralized, an FREE to use, Donations are accepted, but never expected, to support The Contributers of Doginals send any Donations in Dogecoin to the following Contributors:

***You can donate to*** **GreatApe** ***here:***

"𝕏 handle": ***"GreatApe42069"*** "at": [***"@Greatape42069E"***](https://x.com/Greatape42069E)

 **"Đogecoin_address":** **D9pqzxiiUke5eodEzMmxZAxpFcbvwuM4Hg**

