# Development Timeline

Timeline i will use to develop the project, guides on what phases to work on first.

# Development Timeline for FaithFocusFoundation Website

This is a phased approach, assuming 1-2 developers working part-time (e.g., 10-20 hours/week). Total estimated time: 4-6 weeks. Adjust based on experience.

## Phase 1: Setup and Planning (Week 1)

- **Duration**: 2-3 days
- **Tasks**:
  - Initialize Git repository.
  - Set up folder structure as per project blueprint.
  - Configure Composer: Run `composer init`, add dependencies (PHPMailer, phpdotenv).
  - Create `.env.example` and `.gitignore`.
  - Write basic `README.md`.
  - Plan database schema (e.g., tables for blogs: id, title, content, created_at; donations: id, amount, donor_info, date).
- **Milestones**: Project skeleton ready; local environment running.

## Phase 2: Core Infrastructure (Week 1-2)

- **Duration**: 4-5 days
- **Tasks**:
  - Implement Database class with PDO connection.
  - Set up routing in `helpers/router.php` and `config/routes.php`.
  - Create base layout (`views/layouts/main.php`) with header/footer.
  - Add .htaccess for URL rewriting and security headers.
  - Implement global helpers (e.g., sanitize functions).
- **Milestones**: Basic routing works; DB connection tested.

## Phase 3: Static Pages and Frontend (Week 2)

- **Duration**: 3-4 days
- **Tasks**:
  - Build Home, About, Programs pages (static views).
  - Integrate Bootstrap/CSS for responsive design.
  - Add assets (images, JS for simple interactions).
- **Milestones**: Frontend skeleton visible; pages navigable.

## Phase 4: Dynamic Features (Week 3)

- **Duration**: 5-7 days
- **Tasks**:
  - Blog: Models/Controllers/Views for listing, viewing, admin CRUD.
  - Contact Form: Validation, email sending with PHPMailer.
  - Donations: Form with payment gateway integration (e.g., Stripe/PayPal redirect; store records in DB).
- **Milestones**: Dynamic content functional; forms submit securely.

## Phase 5: Admin and Security (Week 4)

- **Duration**: 4-5 days
- **Tasks**:
  - Admin dashboard: Session-based auth (login/logout).
  - Protect admin routes.
  - Add CSRF protection to forms.
  - Implement file uploads (e.g., for blog images) with validation.
  - Error handling and logging.
- **Milestones**: Admin area secure; full site testable.

## Phase 6: Testing and Deployment (Week 5-6)

- **Duration**: 3-5 days
- **Tasks**:
  - Write unit tests (e.g., for models/controllers).
  - Manual testing: Forms, DB ops, security checks.
  - Optimize performance (e.g., caching if needed).
  - Deploy to staging/production server.
  - Set up monitoring (e.g., error logs).
- **Milestones**: Site live; bugs fixed.

## Post-Launch

- Monitor for issues.
- Add features like user registrations if needed.
- Regular updates: PHP/dependencies.

Track progress with Git issues or a tool like Trello
