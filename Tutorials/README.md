To host a website locally using **Internet Information Services (IIS)** on Windows, follow these steps:

### 1. Enable IIS on Windows:
1. Open the **Start Menu** and search for "Turn Windows features on or off".
2. In the pop-up window, scroll down and check **Internet Information Services (IIS)**.
3. Expand the **Internet Information Services** tree to check the sub-features you need (for basic website hosting, the default selection is usually sufficient).
4. Click **OK** and wait for the installation to complete.

### 2. Create Your Website Files:
1. Create a folder on your system for your website files. For example, place it in: `C:\inetpub\wwwroot\MyTestWebsite`.
2. Create a simple `index.html` and `styles.css` as your website files.
   - Example `index.html`:
     ```html
     <!DOCTYPE html>
     <html lang="en-us">
     <head>
       <title>Simple Test Website</title>
       <meta charset="utf-8">
       <link rel="stylesheet" href="styles.css">
       <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
     </head>
     <body>
       <div class="nav">
         <nav class="navbar navbar-inverse nav">
           <div class="navbar-header">
             <a class="navbar-brand" href="#">Website</a>
           </div>
           <ul class="nav navbar-nav">
             <li class="active"><a href="#">Home</a></li>
             <li><a href="#">About</a></li>
             <li><a href="#">Contact</a></li>
           </ul>
         </nav>
       </div>
       <div class="container">
         <h1>This is a test website</h1>
       </div>
     </body>
     </html>
     ```
   - Example `styles.css`:
     ```css
     * {
       font-family: sans-serif;
     }
     .nav {
       border-radius: 0 !important;
       color: white;
     }
     .container {
       text-align: center;
       padding: 40px 20px;
     }
     ```

### 3. Add and Configure the Website in IIS:
1. Open **IIS Manager**. Search for "IIS" in the Start Menu to find it.
2. In the left-hand sidebar, expand the **Sites** folder, right-click on it, and select **Add Website**.
3. Fill in the details:
   - **Site Name**: Give it a name (e.g., "My Test Website").
   - **Physical Path**: Navigate to the folder where your website files are stored (e.g., `C:\inetpub\wwwroot\MyTestWebsite`).
   - **Binding**: Select **https** as the type and leave the port as **443**.
   - For **SSL Certificate**, select **IIS Express Development Certificate** (you can change it later for a proper certificate if needed).
4. Click **OK** to create the site.

### 4. Modify Website Settings:
1. In IIS Manager, highlight the new website in the left-hand panel.
2. On the right side, click **Advanced Settings**.
3. Under the **Behavior** section, change **Enabled Protocols** to "https" if it’s not already set.

### 5. Start Your Website:
1. In the right-hand panel, click on **Browse *:443 (https)** to launch your site in the browser.
2. If the browser warns you about the SSL certificate, you can either proceed with the current setup or configure a new certificate later.

### 6. Manage Your Website:
- You can **Stop**, **Start**, or **Restart** the website from the right-hand menu in IIS Manager.

Your site should now be running locally on **https://localhost/**. If you need a more secure SSL certificate, you can follow Microsoft’s documentation on how to set up a valid SSL certificate for local use.