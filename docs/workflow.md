# 🔁 Worklystiq Order Workflow

1. **Client Registers**
   - Fills name, email, phone, password
   - Await admin approval

2. **Admin Approves**
   - Client logs in, creates Order/Quote/Vector

3. **Admin Assigns**
   - Assigns Salesman (if missing), Designer
   - Sets cost → status: `Received`

4. **Designer Uploads**
   - Sees task in dashboard
   - Uploads design files → status: `In Review`

5. **Manager Reviews**
   - Makes changes/adds/replaces → status: `Processed`

6. **Admin Sends Invoice**
   - Client notified, invoice emailed → status: `Released`

7. **Client Reviews & Pays**
   - Can request edits → if not → pays via 2Checkout → status: `Completed`

8. **Notifications**
   - Sent on each stage to relevant users (Socket + Email)
