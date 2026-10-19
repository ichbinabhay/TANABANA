# TANABANA

**Every Thread Tells a Story.**

A responsive, single-file, vanilla-JavaScript marketplace prototype for the college hackathon challenge **Digital Market Access for Local Artisans**.

## Run

Open `index.html` in a modern browser with JavaScript enabled. No installation, API key, build step, or paid service is required. For a consistent origin and reliable browser storage, serve the directory with any free static development server, such as the VS Code Live Server extension or `python3 -m http.server 8080`, then open `http://localhost:8080`.

The application itself is entirely inside `index.html`: markup, custom CSS, seeded data, routing, and JavaScript. Views use hash routes, so refreshing a product, dashboard, or order URL works on a basic static host without rewrite configuration.

Internet access is needed for Google Fonts, the CDN styling runtime, and Pexels stock photographs. System fonts and an in-page image fallback are provided. The site is styled with custom CSS and does not use a frontend component framework.

## Important: Frontend-Only Demo

The provided editing environment has no terminal, server process runner, package manager, or browser automation tool. Consequently, this delivery does **not** include or claim a running Node/Express backend, API endpoints, secure authentication, real payments, or server-side authorization.

All records live in this browser's `localStorage`, under `tanabana-local-demo-v1`. The current mock-checkout token also uses `sessionStorage` when available. The shopping bag and wishlist are shared across local profiles on this device. Do not enter real personal or financial information. Anyone who can access this browser can inspect records, switch roles, or change the data. Client-side role and ownership checks are demo interaction safeguards, not security.

## Try the Demo

Open **Demo mode** at the top or **Demo Workspaces** in the footer. Choose one-click access:

| Workspace | Saved Email | Use |
| --- | --- | --- |
| Customer | `customer@tanabana.demo` | Browse, order, edit a profile, view history |
| Artisan | `artisan@tanabana.demo` | Meera's products, pricing, stories, and fulfilment |
| Admin | `admin@tanabana.demo` | Review applications, pause listings, manage categories |

No password is requested or stored. The email form reopens an existing local profile; it is not authentication. New customer registrations, guest checkouts, and artisan applications create additional local profiles, shown as one-click saved-profile choices on the access screen. Reopen an approved applicant's profile to enter their new artisan studio.

## Features

- Craft-inspired homepage with full-width photography, animated entrances, woven motifs, eight interactive craft categories, featured products, fictional makers, craft storytelling, and customer/artisan process tabs.
- Twelve initial products with stock, prices, descriptions, photos, categories, locations, care instructions, materials, dimensions, techniques, stories, and price allocations.
- Search by product, artisan, category, materials, city, and state. Category, price, and availability filters; price, newest, and popularity sorting; clear and empty states.
- Product details with a two-view gallery, image enlargement, quantity controls, related products, making-process photographs, and transparent sample pricing that sums exactly to the listed price.
- Persistent wishlist and shopping bag with quantity validation, removal, live header counts, and unavailable-stock handling.
- Mock checkout with validated address fields, Demo UPI, Demo Cash on Delivery, optional payment-failure simulation, unique order IDs, item price snapshots, stock deduction, and bag clearing.
- Duplicate-submit guard and checkout-token deduplication. Refreshing confirmation only reads the existing order; it does not create another purchase.
- Guest local-profile creation at checkout, persistent customer order history, per-artisan fulfilment tracking, and eligible customer cancellations with one-time stock restoration.
- Six fictional artisan profiles and four craft-story articles. General Kasuti craft context links to a consulted encyclopedia source; fictional narratives are distinguished from sourced context.
- Validated artisan applications with Pending, Approved, and Rejected demo states. Admin approval creates a new artisan profile and enables that saved local user's studio.
- Artisan dashboard with overview counts, order-derived monthly demo sales, own-product creation, editing, draft/publish controls, deletion, craft-story editing, and profile editing.
- Product image URL or JPEG/PNG/WebP upload. Files up to 5 MB are compressed locally to a maximum dimension of 960 pixels before saving.
- Fulfilment workflow: Pending to Confirmed to Processing to Shipped to Delivered. Artisan/admin cancellation is available before shipping. Each artisan's fulfilment is stored separately, and the customer summary reflects the slowest active fulfilment.
- Admin demo with counts, application review, listing pause/restore, category addition and safe removal, order access, local profile overview, and confirmed data reset.
- FAQ, shipping, returns, privacy, terms, about, locally saved contact messages, and explicitly simulated newsletter sign-ups.
- Responsive navigation and grids, scrollable dashboard tables, native validation, keyboard-focus styles, accessible modal dialogs, live notifications, reduced-motion support, and photo-error fallbacks.
- A **Check demo data** action in Admin Overview and Artisan Help with sixteen live checks for seed content, price allocations, stock, relationships, order totals, unique IDs/tokens, status validity, search, filters, sorting, delivery thresholds, profile emails, and storage integrity.

## Pricing and Stock Rules

All listing and cost inputs use whole INR values. Materials + labour + finishing/packaging + platform fee must exactly equal the listing price. Delivery is INR 99 for non-empty baskets below INR 1,999 and zero for baskets of INR 1,999 or more. Delivery is separate from the product's transparent price breakdown.

Checkout validates every cart item against current publication status and stock before committing one new local state. A failed payment does not change orders, stock, or the bag. Cancelling a fulfilment restores only its items and cannot be repeated after cancellation. Deleting a product does not erase its historical order snapshots.

The browser store is not a transactional multi-client database. Cross-tab updates are observed, but this demo is not safe for concurrent real-world inventory operations, payment processing, or production commerce.

## Presentation Walkthrough

1. Start on Home, select Kasuti Embroidery, search for Meera or Dharwad, change price limits and sorting, and open a product.
2. Read The Story Woven In and the sample cost breakdown. Try gallery thumbnails, image enlargement, related products, and wishlist controls.
3. Add the cushion to the bag. Change its quantity, remove an item, and verify totals and the live item count. Refresh to verify persistence.
4. Open checkout using sample details such as `Aanya Demo`, `9000000000`, `12 Sample Lane`, `Bengaluru`, `Karnataka`, and `560001`.
5. Select the failure-test checkbox and submit. Confirm an error appears without an order or stock change. Uncheck it and submit again.
6. Note the unique order ID, view tracking/history, and refresh the confirmation URL. Confirm that only one order exists and the bag remains empty.
7. Switch to Artisan and view Orders. Move the relevant fulfilment through its next allowed states. Switch back to the original customer profile to see updated tracking.
8. In Artisan, add a product with all required details and an image. Enter matching cost allocations or use the calculated-total button. Save a draft, edit it, publish it, unpublish it, and delete it with confirmation.
9. Submit an artisan application with a new fictional name and email. Note Pending status. Switch to Admin, approve it, and open the applicant's saved email to enter the newly enabled studio. Use another application to demonstrate rejection.
10. As Admin, pause and restore a listing. Add a category, remove that unused category, and verify that categories already used by products or makers cannot be removed.
11. Try an out-of-stock product, empty search, invalid phone/PIN, quantity exceeding stock, and mismatched pricing. Verify useful errors and unchanged data.
12. Test widths around 1440, 1024, 768, 390, and 360 pixels. Test the mobile menu, modal dismissal, keyboard focus, forms, grids, and horizontal scrolling inside tables only.
13. Run Check demo data. Use Reset local demo data for a clean presentation state.

## Verification Status

Implementation and static source review are provided. The workspace does not expose a browser, JavaScript runtime, terminal, or test runner, so no automated execution, screenshot validation, live CDN check, or manual browser workflow completion is claimed. The walkthrough above and built-in data checks are supplied for verification in a real browser.

There are **no protected production operations** to test: no backend is delivered. Directly navigating to another local role's view is guarded for demo flow only. All roles are intentionally open through the demo chooser. Production authorization must be implemented and tested on a server, never inferred from these frontend checks.

## Required Before Production

- A Node.js/Express service with validated product, artisan, application, order, and authentication endpoints, called using Fetch.
- Secure sessions or equivalent authentication, server-side role enforcement, and artisan ownership checks on every protected read and write.
- Transactional persistent storage, safe concurrent stock updates, order idempotency, audit records, and protection of customer delivery information.
- A real payment provider with verified server-side callbacks; no client-side flag should establish payment success.
- Real artisan consent and verified product photography, provenance, prices, and cultural statements; production-ready privacy, returns, shipping, and terms policies.
- Upload validation, storage quotas, content moderation, secure deployment, error monitoring, and automated accessibility, functional, mobile, and authorization tests.

## Credits and Content Notes

Photography is loaded from Pexels. The named fictional makers are not the people pictured, and process images are representative, not evidence of location or provenance. The consulted general Kasuti reference is the Impart Encyclopedia of Art:

https://imp-art.org/articles/kasuti-embroidery/

"Beedu Craft" is retained as the requested catalogue label but explicitly identified as unverified in its demo story. No authenticity, certification, ethical-sourcing, or sustainability claims are made.