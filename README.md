# eShop Vendor Setup Guide

## Contact
- ⚫️Developer: Attah Kay (SE)
- ⚫️Email: joseph@attakorah.com
- ⚫️Telephone: 0303319900

> **Welcome!** This guide will help you set up and customize your online store. No technical skills required!

---

## 📋 Table of Contents

1. [Getting Started](#getting-started)
2. [Product Setup](#product-setup)
3. [Customizing Your Store](#customizing-your-store)
4. [Managing Content](#managing-content)
5. [Going Live Checklist](#going-live-checklist)
6. [Ongoing Maintenance](#ongoing-maintenance)

---

## 🚀 Getting Started

### What You'll Need

- ✅ Google Account (for Google Sheets access)
- ✅ Cloudinary Account (free tier available for image hosting)
- ✅ Product photos (high quality, well-lit images)
- ✅ Product information (titles, descriptions, prices)
- ✅ Business information (contact details, policies, etc.)

### Your Store Components

Your eShop consists of:
1. **Product Catalog** - Managed via Google Sheets
2. **Images** - Hosted on Cloudinary
3. **Content Pages** - Terms, Privacy, About, Contact, FAQ
4. **Campaign Settings** - Ticker messages and video section

---

## 🛍️ Product Setup

### Method 1: Google Form (Recommended for Beginners)

**Step 1: Access Your Product Form**
- You'll receive a link to a Google Form
- This form is connected to your product Google Sheet

**Step 2: Fill Out Product Information**
For each product, provide:
- **Title** - Product name (e.g., "Women's Leather Handbag")
- **Short Description** - Brief 1-2 sentence summary
- **Full Description** - Detailed product information
- **Price** - Number only (e.g., 250.00)
- **Currency** - Use `GH₵` for Ghana Cedis
- **Category** - Product category (e.g., Fashion, Electronics, Home & Living)
- **Tags** - Comma-separated keywords (e.g., leather, handbag, women, fashion)
- **SKU** - Unique product code (e.g., LHB-001)
- **Main Image URL** - Link to your main product photo on Cloudinary
- **Gallery Images** - Additional image URLs separated by `|` (pipe symbol)
- **In Stock** - TRUE or FALSE
- **Featured** - TRUE (shows in hero carousel) or FALSE

**Step 3: Upload Your Images to Cloudinary First**

Before filling the form:
1. Go to [Cloudinary.com](https://cloudinary.com)
2. Sign up for a free account
3. Upload your product images
4. Copy the image URLs
5. Paste URLs into the form

**Step 4: Submit the Form**

Once submitted, your product appears on your website within 5 minutes (cache refresh time).

---

### Method 2: Direct Google Sheet Editing (Advanced)

**Step 1: Access Your Google Sheet**
- You'll receive a link to your Google Sheet named "Products"
- Request edit access if needed

**Step 2: Understand the Sheet Structure**

Your sheet has these columns:

| Column | Description                        | Example | Required |
|--------|------------------------------------|---------|----------|
| `id` | Unique product ID (auto generated) | `prod-001` | ✅ Yes |
| `title` | Product name                       | `Handcrafted Leather Bag` | ✅ Yes |
| `shortDescription` | Brief summary                      | `Premium leather handbag` | ✅ Yes |
| `description` | Full details                       | `Handcrafted from genuine...` | ✅ Yes |
| `price` | Price (numbers only)               | `350.00` | ✅ Yes |
| `currency` | Currency symbol                    | `GH₵` | ✅ Yes |
| `category` | Product category                   | `Fashion` | ✅ Yes |
| `tags` | Keywords (comma-separated)         | `leather,handbag,women` | ❌ No |
| `sku` | Stock keeping unit                 | `LHB-001` | ✅ Yes |
| `mainImage` | Main product photo URL             | `https://res.cloudinary.com/...` | ✅ Yes |
| `galleryImages` | Additional photos (pipe-separated) | `url1\|url2\|url3` | ❌ No |
| `featured` | Show in hero carousel              | `TRUE` or `FALSE` | ✅ Yes |
| `inStock` | Product availability               | `TRUE` or `FALSE` | ✅ Yes |
| `dateAdded` | When added                         | `2024-01-15` | ✅ Yes |

**Step 3: Add Products**

1. Each row = one product
2. Keep the header row (row 1) unchanged
3. Fill in all required columns
4. Use proper formatting:
   - Tags: `fashion,women,handbag` (comma-separated, no spaces)
   - Gallery images: `url1|url2|url3` (pipe-separated)
   - Featured/InStock: `TRUE` or `FALSE` (all caps)

**Step 4: Save and Wait**

- Changes appear within 5 minutes
- Google Sheets auto-saves
- Your website refreshes its cache automatically

---

## 🎨 Customizing Your Store

### 1. Brand Information

**What to Update:**
- Store name (in code: `BRAND_NAME`)
- Contact phone number
- WhatsApp number for orders
- Email address

**Where:** Contact your developer to update these in the codebase.

---

### 2. Ticker Messages (Announcements)

**What:** Scrolling messages at top of homepage (e.g., "Free shipping over GH₵200")

**How to Manage:**

**Option A: Google Sheet (campaign)**
1. Open the "campaign" sheet in your Google Sheets
2. Add messages in column A (one per row)
3. Optional: Add header "message" in row 1
4. Save - changes appear in 5 minutes

**Example:**
```
message
Free shipping on orders over GH₵200
New arrivals every Monday
Shop now, pay later available
```

**Turn Off Ticker:**
- Delete all messages from the sheet
- Ticker automatically hides when empty

---

### 3. Video Hero Section

**What:** Full-screen video section on homepage

**How to Manage:**

**Option A: Google Sheet (video)**
1. Open the "video" sheet in your Google Sheets
2. Use this format:

**Key-Value Format:**
```
key         | value
videoUrl    | https://your-video-url.mp4
posterUrl   | https://your-poster-image.jpg
title       | Experience the Difference
description | Where quality meets affordability
ctaText     | Shop Now
ctaLink     | /#products
```

**OR Header-Row Format:**
```
videoUrl | posterUrl | title | description | ctaText | ctaLink
https:// | https://  | ...   | ...         | ...     | ...
```

**Turn Off Video:**
- Delete all data from the video sheet
- Falls back to default video

**Video Requirements:**
- Format: MP4
- Recommended size: Under 10MB
- Dimensions: 1920x1080 or higher
- Host on Cloudinary or imagekit

---

## 📝 Managing Content

### Pages to Customize

You'll need to review and update these pages with your business information:

#### 1. **About Page** (`/about`)
**What to Update:**
- Your story
- Mission statement
- Company values
- What makes you different

**How:** Send your content to your developer for updates.

---

#### 2. **Terms of Service** (`/terms`)
**What to Update:**
- Business name throughout
- Return policy details
- Shipping policies
- Payment terms specific to your business

**How:** Review the default template and provide your specific terms.

**Important Sections:**
- Return/refund timeframes
- Shipping costs and delivery times
- Payment methods accepted
- Order cancellation policy

---

#### 3. **Privacy Policy** (`/privacy`)
**What to Update:**
- How you collect customer data
- What data you collect
- How you use customer information
- Third-party services you use

**How:** Review and modify the template with your actual practices.

**Ghana-Specific Considerations:**
- Comply with Data Protection Act, 2012 (Act 843)
- Mention if you share data with delivery services
- Clarify mobile money payment data handling

---

#### 4. **FAQ Page** (`/faq`)
**What to Update:**
- Your actual delivery times (by region)
- Your payment methods
- Your return policy specifics
- Your customer service hours

**Categories to Cover:**
- Orders & Shipping
- Returns & Refunds
- Products
- Account & Support

**How:** Send updated Q&A content to your developer.

---

#### 5. **Contact Page** (`/contact`)
**What to Update:**
- Business address (if you have a physical location)
- WhatsApp number
- Email address
- Business hours
- Location details

**Current Default:**
- WhatsApp: +233 20 175 0533
- Location: Accra, Ghana
- Hours: Monday-Saturday, 9 AM - 6 PM GMT

---

## ✅ Going Live Checklist

Before launching your store:

### Products
- [ ] At least 10-15 products added to Google Sheet
- [ ] All product images uploaded to Cloudinary
- [ ] Product descriptions are complete and accurate
- [ ] Prices are correct and include currency (GH₵)
- [ ] At least 2-3 products marked as "Featured" (for hero carousel)
- [ ] All products have valid SKUs
- [ ] Stock status is accurate (inStock: TRUE/FALSE)

### Images
- [ ] Images are high quality (minimum 800x800px)
- [ ] Images show products clearly
- [ ] Images are well-lit and professional
- [ ] Multiple angles provided (gallery images)
- [ ] All images hosted on Cloudinary
- [ ] Image URLs are public and accessible

### Content Pages
- [ ] About page reviewed and customized
- [ ] Terms of Service updated with your policies
- [ ] Privacy Policy reflects your data practices
- [ ] FAQ answers your common customer questions
- [ ] Contact page has correct information

### Settings
- [ ] Brand name is correct
- [ ] WhatsApp number is your business number
- [ ] Contact email is monitored
- [ ] Ticker messages are relevant (or disabled)
- [ ] Video section configured (or using default which you should provide)

### Testing
- [ ] Browse website on mobile phone
- [ ] Test add to cart functionality
- [ ] Complete a test order via WhatsApp
- [ ] Check all links work
- [ ] Verify images load properly
- [ ] Test search functionality

### Legal & Business (this is not really my business though 😂)
- [ ] Business registration complete
- [ ] Have return/refund process in place
- [ ] Shipping partners confirmed
- [ ] Payment methods set up (mobile money, etc.)
- [ ] Customer service process ready

---

## 🔄 Ongoing Maintenance

### Daily Tasks
- Check WhatsApp for orders
- Respond to customer inquiries
- Update stock status if items sell out

### Weekly Tasks
- Add new products (if available)
- Review and respond to customer questions
- Update ticker messages with promotions
- Check that all images are loading

### Monthly Tasks
- Review FAQ and update common questions
- Add seasonal products
- Update featured products in carousel
- Review pricing and adjust if needed
- Check analytics (if enabled)

---

## 📊 Product Management Best Practices

### Product Titles
- ✅ **Good:** "Women's Leather Crossbody Bag - Brown"
- ❌ **Bad:** "bag"
- Keep titles clear and descriptive
- Include key features (color, size, material)
- Use proper capitalization

### Descriptions
- Start with key benefits
- Include materials and dimensions
- Mention care instructions
- Highlight what makes it special
- Keep it scannable (use short paragraphs)

### Pricing
- Always use `.00` format (e.g., 250.00, not 250)
- Be consistent with currency (GH₵)
- Consider shipping costs in pricing
- Research competitor pricing
- Update during sales/promotions

### Images
- **Main Image:** Hero shot, product centered
- **Gallery Images:**
  - Multiple angles
  - Close-ups of details
  - Product in use (if applicable)
  - Size comparison
- Minimum 3-5 images per product recommended

### Categories
Common categories:
- Fashion & Apparel
- Electronics
- Home & Living
- Beauty & Personal Care
- Food & Beverages
- Books & Stationery
- Sports & Outdoors
- Toys & Games
- Health & Wellness

Choose categories that make sense for your products.

### Tags
- Use 3-8 relevant tags per product
- Include material (leather, cotton, plastic)
- Include use case (gift, everyday, formal)
- Include target audience (men, women, kids)
- Include style (modern, vintage, casual)

**Example for a handbag:**
`leather,handbag,women,crossbody,brown,fashion,gift`

---

## 🆘 Common Issues & Solutions

### "My products aren't showing up"
**Solutions:**
1. Wait 5 minutes for cache to refresh
2. Check Google Sheet has no errors
3. Verify all required columns are filled
4. Ensure image URLs are accessible (open in browser)
5. Check that `inStock` is set to `TRUE`

### "Images won't load"
**Solutions:**
1. Verify Cloudinary URLs are public
2. Check URLs don't have typos
3. Ensure images were uploaded successfully
4. Try opening the URL in a new browser tab
5. Re-upload image to Cloudinary if needed

### "Changes aren't appearing"
**Solutions:**
1. Clear your browser cache (Ctrl+Shift+R or Cmd+Shift+R)
2. Wait the full 5 minutes for cache refresh
3. Try viewing in incognito/private window
4. Check Google Sheet was actually saved

### "Product photos look blurry"
**Solutions:**
1. Upload higher resolution images (minimum 1200px width)
2. Compress images without losing quality (use TinyPNG.com)
3. Ensure images are sharp before uploading
4. Use proper lighting when photographing products

### "Hero carousel is empty"
**Solutions:**
1. Mark at least 1-2 products as `featured: TRUE`
2. Ensure featured products have images
3. Wait for cache to refresh
4. Fallback hero section will show if no featured products

---

## 💡 Tips for Success

### Photography Tips
- Use natural lighting when possible
- Plain white or neutral backgrounds work best
- Show product scale (place common object nearby)
- Include lifestyle shots (product being used)
- Maintain consistent photo style across all products

### Writing Product Descriptions
- Answer: What is it? Who is it for? Why buy it?
- Use bullet points for features
- Include dimensions/size info
- Mention what's included (packaging, accessories)
- Use conversational, friendly tone

### Pricing Strategy
- Research competitors
- Factor in:
  - Product cost
  - Cloudinary costs
  - Shipping costs
  - Payment processing fees (if any)
  - Your profit margin
- Consider psychological pricing (GH₵99 vs GH₵100)

### Customer Service
- Respond to WhatsApp messages within 2 hours
- Be friendly and professional
- Set clear expectations for delivery
- Follow up after delivery
- Handle complaints gracefully

---

## 📞 Getting Help

### Technical Issues
Contact your developer for:
- Code changes
- Custom features
- Website not loading
- Error messages
- Payment integration issues

### Content Updates
You can update yourself:
- Product information (via Google Sheets)
- Ticker messages (via Google Sheets)
- Video section (via Google Sheets)
- Product images (via Cloudinary)

Contact developer for:
- Page content (About, Terms, Privacy, FAQ, Contact)
- Brand name changes
- WhatsApp number changes
- Major design changes

### Where to Find Your Developer
- Developer contact: joseph@attakorah.com
- Support hours: [9-5]
- Response time: Depends on how much you're paying

---

## 📚 Resources

### Free Tools
- **Image Compression:** [TinyPNG.com](https://tinypng.com)
- **Image Editing:** [Canva.com](https://canva.com) (free tier)
- **Image Hosting:** [Cloudinary.com](https://cloudinary.com) (free tier)
- **imagekit:** [imagekit.io](https://unsplash.com) (free tier)
- **Stock Photos:** [Unsplash.com](https://unsplash.com) (for inspiration)

### Learning Resources
- [Google Sheets Basics](https://support.google.com/docs/topic/9054603)
- [Product Photography Tips](https://www.shopify.com/blog/product-photography)
- [Writing Product Descriptions](https://www.bigcommerce.com/blog/product-descriptions/)

### Ghana E-Commerce Resources
- Ghana Revenue Authority (Tax compliance)
- Ghana Post GPS (Address system)
- Mobile Money Operators (MTN, Vodafone, AirtelTigo)

---

## 🎯 Next Steps

1. Set up accounts (Google, Cloudinary)
2. Photograph products and upload to Cloudinary
3. Add products to Google Sheet (start with 10-15)
4. Review and customize content pages
5. Test everything and go live!

---

**Questions?** Contact your developer or refer to the technical documentation in the `/guidelines` folder.

**Good luck with your store! 🎉**

---

*Last updated: November 17, 2025*
*Version: 1.0*
