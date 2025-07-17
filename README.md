# 🚀 NS-Tech Website - Google Forms Contact Integration

## ✅ What You Get:

- **100% Free** - No hosting, PHP, or email costs
- **Direct Integration** - Contact form submits directly to Google Forms from main page
- **Instant Setup** - Works in 5 minutes
- **Email Notifications** - Get alerts when someone submits
- **Response Tracking** - View all responses in Google Sheets
- **No Maintenance** - Google handles everything

## 🎯 Current Status:

**✅ READY TO USE:** Your contact form on `index.html` is already set up and working!

When someone fills out the contact form on your main website:
1. ✅ Form submits directly to Google Forms
2. ✅ User sees success message (no page refresh)
3. ✅ Response is saved to Google Forms
4. ✅ You get email notification (if enabled)

## 🔧 Setup Your Own Google Form (Optional):

Currently using example Google Form. To connect your own:

### Step 1: Create Google Form 

1. **Go to:** https://forms.google.com/
2. **Click "Blank"** to create new form
3. **Add these questions:**
   - **Question 1:** "Name" (Short answer, Required)
   - **Question 2:** "Email" (Short answer, Required)
   - **Question 3:** "Message" (Paragraph, Required)
4. **Click "Send"** button (top right)

### Step 2: Get Form Action URL

1. **Click "Send"** → **Link tab** → **Copy link**
2. **Open the link** in new tab (your live form)
3. **Right-click** → **"View Page Source"**
4. **Press Ctrl+F** and search for: `action="`
5. **Copy the URL** that comes after `action="` (ends with `/formResponse`)

**Example:** `https://docs.google.com/forms/d/e/1FAIpQLSe.../formResponse`

### Step 3: Get Field Entry Numbers (Updated Method)

Google Forms now hides the entry numbers in the regular inspect. Here's the correct way:

**🚀 Quick Tool: Use `entry_finder.html`**
- Open `entry_finder.html` in your browser for a step-by-step tool to find entry numbers automatically!

**Method 1: Pre-filled Link (Easiest)**
1. **Go to your Google Form**
2. **Click the three dots (⋮)** → **"Get pre-filled link"**
3. **Fill the form with test data:**
   - Name: `NAME_TEST`
   - Email: `EMAIL_TEST`
   - Message: `MESSAGE_TEST`
4. **Click "Get link"**
5. **Copy the URL** - it will show: `entry.123456789=NAME_TEST&entry.987654321=EMAIL_TEST`
6. **Extract the entry numbers** from the URL

**Method 2: View Page Source**
1. **Go back to your live form**
2. **Right-click** → **"View Page Source"** (not inspect element)
3. **Press Ctrl+F** and search for: `entry.`
4. **Look for patterns like:** `"entry.1234567890"`
5. **Copy the entry numbers** for each field in order (Name, Email, Message)

**Method 3: Network Tab Method**
1. **Open your live form**
2. **Press F12** → **Network tab**
3. **Fill out the form** with test data
4. **Click Submit**
5. **Look for the POST request** to `formResponse`
6. **Check the Form Data** to see the entry numbers

### Step 4: Update Your Contact Form

1. **Open:** `index.html`
2. **Find the contact form section** (around line 415)
3. **Replace these values:**
   - `action="https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse"`
   - `name="entry.YOUR_NAME_ENTRY"` (for name field)
   - `name="entry.YOUR_EMAIL_ENTRY"` (for email field)  
   - `name="entry.YOUR_MESSAGE_ENTRY"` (for message field)

### Step 5: Test Your Form

1. **Open your website:** `index.html`
2. **Fill out the contact form**
3. **Submit** - you should see success message
4. **Check your Google Form responses**

## 📊 View Responses:

1. **Open your Google Form**
2. **Click "Responses" tab**
3. **Click Google Sheets icon** 📊
4. **All responses appear in spreadsheet automatically**

## 🔔 Get Email Notifications:

1. **In your Google Form responses**
2. **Click "More" (3 dots) → "Get email notifications for new responses"**
3. **You'll get an email every time someone submits**

## 🛠️ Example Form Setup:

```html
<form action="https://docs.google.com/forms/d/e/1FAIpQLSdX4YQJ6j3LCvFhfxQRGb5KzN8mP9rS2tV7wA1oE4bC6dF9hG/formResponse" method="POST" target="hidden-iframe">
    <input name="entry.1234567890" type="text" placeholder="Name" required>
    <input name="entry.9876543210" type="email" placeholder="Email" required>
    <textarea name="entry.4567890123" placeholder="Message" required></textarea>
    <button type="submit">Send</button>
</form>
<iframe name="hidden-iframe" style="display:none;"></iframe>
```

## 🎉 Benefits:

- ✅ **Works on any website** (no server required)
- ✅ **Instant email notifications**
- ✅ **Automatic spreadsheet logging**
- ✅ **Mobile-friendly**
- ✅ **Spam protection** (Google's built-in)
- ✅ **No coding required**
- ✅ **Free forever**

## � Troubleshooting:

**Form not submitting?**
- Check that action URL ends with `/formResponse`
- Verify entry numbers match your form fields
- Ensure all required fields are filled

**Not receiving emails?**
- Enable email notifications in Google Forms
- Check spam folder
- Verify Google account email settings

**Responses not showing?**
- Check the "Responses" tab in your Google Form
- Create linked Google Sheet for better tracking

## 🚀 Ready-to-Use Files:

- `contact.html` - Working contact form with Google Forms integration
- `index.html` - Main website with contact form
- `README.md` - This setup guide
- `assets/` - Website assets (CSS, JS, images)
- `vendor/` - Bootstrap and jQuery files

## 📱 Mobile-Ready:

The form automatically works on all devices and is fully responsive.

---

**� Your contact form is now 100% free and maintenance-free!**

**No more PHP, hosting costs, or email configuration needed!**


https://docs.google.com/forms/d/e/1FAIpQLScqqfofDSbNf_93a5fDGyrFNUodp9NAH2vrKtc6Stm4B6vmPw/viewform?usp=pp_url&entry.956999181=TEST_NAME&entry.1772718854=1234567890&entry.1756181124=test@example.com&entry.480270753=TEST_MESSAGE