# Xelvora Clothing Store

A clean full-stack clothing ecommerce starter with:

- Responsive storefront with filters, product cards, cart drawer, and checkout flow
- Node.js backend using only built-in modules
- Product catalog API
- Browser admin page for product add/edit/delete
- Server-side order validation
- Local order persistence in `data/orders.json`

## Run Locally

```powershell
npm.cmd start
```

Then open:

```text
http://localhost:3000
```

Admin page:

```text
http://localhost:3000/admin.html
```

## API

```text
GET  /api/health
GET  /api/products
POST /api/orders
POST /api/admin/products
PUT  /api/admin/products/:id
DELETE /api/admin/products/:id
```

## Admin Security

The admin page is password protected.

Local default password:

```text
admin123
```

For a public deployment, set an `ADMIN_PASSWORD` environment variable in Render/Railway. Use a strong password and do not keep the default password online.

Example order payload:

```json
{
  "customer": {
    "name": "Customer Name",
    "email": "customer@example.com",
    "address": "Full delivery address"
  },
  "items": [
    {
      "productId": "linen-overshirt",
      "size": "M",
      "color": "Ivory",
      "quantity": 1
    }
  ]
}
```

## Deployment

### Render

1. Push this folder to GitHub.
2. Create a new Render Web Service.
3. Use these settings:
   - Build command: `npm install`
   - Start command: `npm start`
   - Environment: Node
4. Render will provide a live URL after the first deploy.

### Railway

1. Push this folder to GitHub.
2. Create a Railway project from the repository.
3. Railway detects Node automatically.
4. Set the start command to `npm start` if needed.

### VPS

```powershell
npm install --omit=dev
npm start
```

For production, put the Node app behind Nginx/Caddy and run it with a process manager such as PM2.

## Next Backend Upgrades

- Replace `data/orders.json` with PostgreSQL or MongoDB.
- Add authentication for customers and admins.
- Add payment integration such as Stripe or Razorpay.
- Add an admin dashboard for product, inventory, and order management.
- Move product data into a database table.
