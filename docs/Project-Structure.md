# Project Structure

Commands to create the files in the project folder.

```bash
mkdir -p faithfocusfoundation/{public/assets/{css,js,img},public/uploads,src/{controllers,models,views/{layouts,admin,blog},helpers},config,logs,tests,vendor}
touch faithfocusfoundation/public/{index.php,.htaccess}
touch faithfocusfoundation/src/controllers/{HomeController.php,AboutController.php,BlogController.php,DonationController.php,ContactController.php,AdminController.php}
touch faithfocusfoundation/src/models/{Database.php,BlogModel.php,DonationModel.php,UserModel.php}
touch faithfocusfoundation/src/views/{home.php,about.php,donation.php,contact.php}
touch faithfocusfoundation/src/views/layouts/main.php
touch faithfocusfoundation/src/views/blog/{index.php,show.php}
touch faithfocusfoundation/src/views/admin/dashboard.php
touch faithfocusfoundation/src/helpers/{functions.php,router.php}
touch faithfocusfoundation/config/{app.php,database.php,routes.php}
touch faithfocusfoundation/{.env,.env.example,.gitignore,composer.json,composer.lock,README.md}
touch faithfocusfoundation/tests/ControllerTest.php
```

Here's the visual tree for reference (save as `project-structure.txt`):

```
faithfocusfoundation/                    ← YOUR MAIN PROJECT FOLDER (root; initialize Git here)
├── public/                              ← #1 WEB ROOT: The only publicly accessible folder (set as document root in server config). Browser requests hit here first. Prevents exposing sensitive code.
│   ├── index.php                        ← Main entry point: Routes all incoming requests to controllers. Loads autoloader, config, and handles URL parsing.
│   ├── .htaccess                        ← Apache configuration: Enables clean URLs (e.g., /blog instead of index.php?page=blog), adds security headers (e.g., XSS protection), and forces HTTPS.
│   ├── assets/                          ← Static assets: Files served directly by the browser for frontend.
│   │   ├── css/                         ← CSS subfolder: Styles for the site.
│   │   │   └── main.css                 ← Primary stylesheet: Defines site-wide styles, layouts, and responsiveness (e.g., using Bootstrap).
│   │   ├── js/                          ← JavaScript subfolder: Scripts for client-side interactions.
│   │   │   └── main.js                  ← Primary script: Handles things like form validation, AJAX calls, or simple animations (vanilla JS or jQuery).
│   │   └── img/                         ← Images subfolder: Static images for the site.
│   │       └── logo.png                 ← Example image: Site logo or banners (add more as needed for pages like home or about).
│   └── uploads/                         ← User uploads: Stores files uploaded via forms (e.g., blog images). Secure with permissions (e.g., 755) and validate uploads in code.
├── src/                                 ← #2 SOURCE CODE: Core PHP logic. Hidden from web access for security. Contains the "brain" of the app.
│   ├── controllers/                     ← #3 CONTROLLERS: Handle user requests, process data (from models), and render views. One per major feature.
│   │   ├── HomeController.php           ← Manages home page: Fetches any dynamic data (e.g., recent blogs) and loads home view.
│   │   ├── AboutController.php          ← Manages about page: Static or dynamic content about the NGO.
│   │   ├── BlogController.php           ← Manages blog: Handles listing, viewing, creating/editing/deleting posts (CRUD for admins).
│   │   ├── DonationController.php       ← Manages donations: Processes forms, integrates with payment gateways (e.g., Stripe redirect), stores records.
│   │   ├── ContactController.php        ← Manages contact: Validates form, sends emails via PHPMailer.
│   │   └── AdminController.php          ← Manages admin dashboard: Handles login/logout, auth checks, and admin-specific actions.
│   ├── models/                          ← #4 MODELS: Interact with the database. Define data structures and queries (using PDO for security).
│   │   ├── Database.php                 ← DB connection: Singleton class for PDO setup, connects using .env credentials, handles queries securely.
│   │   ├── BlogModel.php                ← Blog data: Methods for fetching/inserting/updating/deleting blog posts (e.g., getAllPosts(), createPost()).
│   │   ├── DonationModel.php            ← Donation data: Methods for storing donation records (e.g., logDonation()).
│   │   └── UserModel.php                ← User/auth data: Handles admin users (e.g., checkLogin(), getUserByUsername() with password verification).
│   ├── views/                           ← #5 VIEWS: HTML templates with PHP embeds for dynamic content. No heavy logic here – just display.
│   │   ├── layouts/                     ← Reusable layouts: Base templates for consistent structure.
│   │   │   └── main.php                 ← Main layout: Includes header, footer, navigation; wraps page-specific content.
│   │   ├── home.php                     ← Home view: Displays mission, highlights, perhaps a blog teaser.
│   │   ├── about.php                    ← About view: NGO history, team info.
│   │   ├── blog/                        ← Blog subviews: Specific to blog feature.
│   │   │   ├── index.php                ← Blog list: Loops through posts to display summaries.
│   │   │   └── show.php                 ← Single blog: Displays full post content.
│   │   ├── donation.php                 ← Donation view: Form for donations, perhaps with amount options.
│   │   ├── contact.php                  ← Contact view: Form for user inquiries.
│   │   └── admin/                       ← Admin subviews: Secured pages.
│   │       └── dashboard.php            ← Admin dashboard: Interface for managing content (e.g., add/edit blogs).
│   └── helpers/                         ← #6 HELPERS: Utility functions shared across the app.
│       ├── functions.php                ← Global utilities: Functions like sanitize_input(), generate_csrf_token() for security/validation.
│       └── router.php                   ← Routing logic: Maps URLs to controllers (e.g., simple switch or array-based router).
├── config/                              ← #7 CONFIG: Non-secret settings and routes.
│   ├── app.php                          ← App config: General settings like site name, base URL, debug mode.
│   ├── database.php                     ← DB config: Loads .env vars and defines connection params (but no secrets here).
│   └── routes.php                       ← Routes: Defines URL mappings (e.g., '/' => HomeController).
├── logs/                                ← #8 LOGS: Error and app logs (gitignore this; auto-created if using Monolog).
│   └── error.log                        ← Example log: Records PHP errors or custom logs.
├── tests/                               ← #9 TESTS: Unit/integration tests (optional but good practice).
│   └── ControllerTest.php               ← Example test: PHPUnit tests for controllers (e.g., testHomePageLoads()).
├── vendor/                              ← #10 VENDOR: Auto-generated by Composer. Contains installed dependencies (gitignore).
│   (folders like phpmailer/, vlucas/)   ← Installed packages: E.g., PHPMailer for emails, phpdotenv for .env.
├── .env                                 ← #11 ENV: Secret environment variables (gitignore; never commit).
├── .env.example                         ← Env template: Placeholder file with dummy values (commit this).
├── .gitignore                           ← Git ignore: Lists files/folders to exclude from repo (e.g., .env, vendor/, logs/).
├── composer.json                        ← #12 COMPOSER.JSON: Dependency manifest – lists required packages.
├── composer.lock                        ← Composer lock: Pins exact versions of dependencies for consistency.
└── README.md                            ← Documentation: Project overview, setup instructions (as we created earlier).
```


