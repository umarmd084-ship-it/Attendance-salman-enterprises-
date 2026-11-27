# Mohd Umar x Salman Enterprises - Staff, Shops, Sale & Collection

## What it does
- Office attendance (check-in / check-out within 50m of office)
- Admin creates staff -> creates shops -> maps each shop to a salesman (change anytime)
- Salesman logs in and sees ONLY his own shops, logs visit with Sale and Collection amount
- "Shop Sale & Collection" report: shop-wise totals, date filter, CSV download
- Data is saved in MongoDB Atlas (shared across all phones)

## Files
- index.html  - the whole app
- package.json - installs the mongodb driver on Vercel
- api/_db.js, api/state.js, api/health.js - connect to MongoDB Atlas

## Deploy (same as before)
1. Upload index.html, package.json and the api folder to GitHub (replace old files).
2. Vercel -> Import repository -> add Environment Variable MONGODB_URI = your mongodb+srv:// link -> Deploy.
3. Open /api/health -> must show "MongoDB Atlas connected".
4. Login admin@salmanenterprises.in / Admin@123, then in "1. Manage Staff & Logins" click Change Password.

## Daily use order
1. Manage Staff & Logins -> create every salesman
2. Shops & Salesman Mapping -> add shop, pick salesman (later change from dropdown)
3. Salesmen login on phone -> Check-In -> Log Shop Visit (sale + collection)
4. Admin -> Shop Sale & Collection to see totals
