# Recipe Landing Page

A beautiful, conversion-optimized landing page for collecting emails in exchange for a free recipe.

## Features

- Clean, modern design
- Mobile-responsive
- Email capture form
- Smooth animations
- Thank you page after submission
- Integration with n8n webhook for automation

## Customization Guide

### 1. Update Branding

Replace `YOUR BRAND` in the header (line 344) with your brand name.

### 2. Customize the Content

**Badge** (line 351):
```html
<span class="badge">Free Recipe</span>
```

**Headline** (line 353):
```html
<p class="headline">The recipe everyone's been asking for</p>
```

**Main Title** (line 355):
```html
<h1>Get the Secret Recipe</h1>
```

**Description** (line 357):
```html
<p class="description">Simple ingredients. <span class="highlight">Amazing results</span>. The perfect dish for any occasion.</p>
```

### 3. Add Recipe Image

Replace the placeholder (line 361) with your recipe image:
```html
<div class="recipe-preview">
    <img src="your-recipe-image.jpg" alt="Your Recipe Name">
</div>
```

### 4. Update Benefits

Edit the benefits list (lines 367-376) to match what your recipe offers:
```html
<li>Your benefit here</li>
```

### 5. Configure n8n Webhook

Update the webhook URL (line 473) to match your n8n automation:
```javascript
const response = await fetch('https://YOUR-N8N-URL.app.n8n.cloud/webhook/recipe', {
```

### 6. Customize Colors

The color scheme is defined in CSS variables (lines 14-22):
```css
:root {
    --primary: #1a1a1a;      /* Main text color */
    --secondary: #d4614f;    /* Accent color (red/orange) */
    --accent: #f4a261;       /* Button color */
    --bg: #fafafa;           /* Background */
    --white: #ffffff;        /* White */
    --text: #2a2a2a;        /* Body text */
    --light-text: #666;      /* Lighter text */
    --border: #e0e0e0;       /* Borders */
}
```

### 7. Footer

Update the footer (line 427) with your brand name and year.

## n8n Webhook Setup

The form sends the following data:
```json
{
    "firstName": "User's first name",
    "email": "user@example.com",
    "submittedAt": "2025-01-19T12:00:00.000Z",
    "source": "recipe-landing-page"
}
```

Set up your n8n workflow to:
1. Receive the webhook
2. Send the recipe via email
3. Add the email to your mailing list (optional)

## Deployment

This is a static HTML page. You can deploy it to:
- GitHub Pages
- Netlify
- Vercel
- Any web hosting service

Simply upload the `index.html` file to your hosting provider.

## Testing

1. Open `index.html` in your browser
2. Click "Get Your Free Recipe"
3. Fill in the form
4. Verify the webhook receives the data
5. Check that the thank you page appears

## Support

For issues or questions, refer to the n8n documentation for webhook setup.
