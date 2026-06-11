🍲 Love and Luto

Welcome to the official repository for Love and Luto, an online menu and ordering platform for home-cooked Filipino goodness, based in Auckland, New Zealand.

This website serves as a digital menu where customers can browse authentic dishes, add items to their cart, select dates, and instantly forward their orders via WhatsApp or SMS.

🚀 Live Preview

Your site is (or will be) live at: https://[your-username].github.io/love-and-luto/

📂 Project Structure

index.html - The main, single-page application containing the entire menu, shopping cart logic, and animations.

config.html - A private, local tool used to generate HTML code for new menu items.

images/ - (Create this folder) This is where you should drop all your local .jpg or .png images.

logo.png - The primary logo file for your site.

🛠️ How to Edit the Menu

Because this is a static website (hosted for free on GitHub Pages), there is no backend database. However, adding and removing items is incredibly easy.

1. Adding a New Item

Open config.html in your web browser.

Fill out the form with your new dish's details (Name, Description, Prices, Tags).

Click "Generate Code".

Copy the generated HTML block.

Open index.html in a text editor (or directly in GitHub).

Find the section you want (e.g., <!-- Breads -->, <!-- Viands -->).

Paste the code right below the other items in the <div class="grid grid-cols-1 ..."> container.

2. Marking an Item as "Sold Out"

Find the HTML block for the food item in index.html and look for the first line of that block. Change data-available="true" to "false":

<div class="reveal item-card..." data-available="false">


The website will automatically add a red heart "SOLD OUT" badge and disable the add-to-cart buttons.

3. Updating Images

Scroll to the bottom of index.html and look for the SITE_IMAGES configuration block. Update the filename to match the image you dropped into your images/ folder.

const SITE_IMAGES = {
    "my-new-dish": "images/my-new-dish-photo.jpg"
};


Then, make sure the data-img-key in your HTML matches that exact name!

📱 Checkout Logic

This application uses a pure front-end checkout process. It compiles the user's cart data, subtotal, and delivery details into a neatly formatted string, and injects it into a WhatsApp API URL or an SMS protocol to send directly to your phone.
