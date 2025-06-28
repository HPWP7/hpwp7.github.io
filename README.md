# ITEna Solutions - Modern Static Website

A modern, responsive static website for ITEna Solutions, converted from the original CMS-based site into a single HTML file optimized for GitHub Pages deployment.

## 🌟 Features

- **Single HTML File**: All CSS and JavaScript embedded for easy deployment
- **Fully Responsive**: Mobile-first design that works on all devices
- **Modern Design**: Clean, professional appearance with smooth animations
- **Hero Slider**: Interactive slider showcasing the three main solutions
- **Smooth Animations**: Fade-in effects and scroll animations
- **SEO Optimized**: Proper meta tags and semantic HTML structure
- **Fast Loading**: Optimized CSS/JS with efficient image handling

## 📋 Content Sections

### Header
- Logo and responsive navigation menu
- Smooth scroll to sections
- Mobile hamburger menu

### Hero Slider
1. **Insurance Central** - Insurance solution for Cyprus market
2. **Money Transfer Central** - Master-agent/sub-agent model solution  
3. **Custom Development** - ITEna Application host framework

### Main Sections
- **About Us**: Company description with "We Make Technology Work For YOU!" tagline
- **Services**: 5 main services with icons and descriptions
- **Statistics**: 30+ Enterprise Clients, 700+ Internal Users, 3000+ Web Users
- **Success Message**: Client relationship section
- **Footer**: Contact information and quick links

## 🚀 GitHub Pages Deployment

### Method 1: Direct Upload
1. **Create a new GitHub repository**
   ```
   Repository name: itenasolutions-website
   Description: ITEna Solutions company website
   Set to Public
   ```

2. **Upload files**
   - Upload `index.html` to the root of your repository
   - Upload the entire `images/` folder
   - Upload `data/` folder (optional, for reference)

3. **Enable GitHub Pages**
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)
   - Click Save

4. **Access your website**
   - Your site will be available at: `https://yourusername.github.io/itenasolutions-website`
   - It may take a few minutes to go live

### Method 2: Git Command Line
1. **Clone and setup**
   ```bash
   git clone https://github.com/yourusername/itenasolutions-website.git
   cd itenasolutions-website
   
   # Copy your files
   cp /path/to/index.html .
   cp -r /path/to/images/ .
   ```

2. **Commit and push**
   ```bash
   git add .
   git commit -m "Initial website deployment"
   git push origin main
   ```

3. **Enable GitHub Pages** (follow step 3 above)

## 📁 File Structure

```
itenasolutions-website/
├── index.html              # Main website file (single HTML)
├── images/                  # All website images
│   ├── hero-insurance.jpg   # Hero slider image 1
│   ├── hero-money-transfer.jpg # Hero slider image 2
│   ├── hero-custom-dev.jpg  # Hero slider image 3
│   ├── about-section.jpg    # About section image
│   ├── hero-bg.jpg         # Background image
│   ├── icon-insurance.jpg   # Service icon
│   ├── icon-money-transfer.jpg # Service icon
│   ├── icon-broker.jpg     # Service icon
│   ├── icon-payment.jpg    # Service icon
│   └── icon-custom-dev.jpg # Service icon
├── data/                   # Original content data (optional)
│   └── content.json        # Extracted website content
└── README.md              # This file
```

## 🔧 Customization Guide

### Updating Content

All content is embedded in `index.html`. Here's how to update different sections:

#### 1. Company Information
**Location**: Header and footer sections
```html
<!-- Update company name in header -->
<a href="#" class="logo">Your Company Name</a>

<!-- Update contact info in footer -->
<p>Your Address Here</p>
<p>Email: <a href="mailto:your@email.com">your@email.com</a></p>
<p>Phone: <a href="tel:yourphone">Your Phone</a></p>
```

#### 2. Hero Slider Content
**Location**: Lines ~300-330
```html
<div class="slide-content">
    <h2>Your Service Title</h2>
    <p>Your service description here...</p>
    <a href="#services" class="btn">Learn More</a>
</div>
```

#### 3. Services Section
**Location**: Lines ~380-420
```html
<div class="service-card">
    <div class="service-icon">
        <img src="./images/your-icon.jpg" alt="Your Service">
    </div>
    <h3>Your Service Name</h3>
    <p>Your service description...</p>
</div>
```

#### 4. Statistics
**Location**: Lines ~440-460
```html
<span class="stat-number">Your Number+</span>
<div class="stat-label">Your Label</div>
```

### Changing Colors

Update the CSS variables at the top of the `<style>` section:

```css
:root {
    --primary-color: #2c3e50;    /* Dark blue/gray */
    --secondary-color: #3498db;   /* Light blue */
    --accent-color: #e74c3c;      /* Red accent */
    --text-primary: #2c3e50;      /* Dark text */
    --text-secondary: #7f8c8d;    /* Light text */
    --background-light: #ecf0f1;  /* Light background */
}
```

### Adding New Images

1. Add images to the `images/` folder
2. Update the HTML image paths:
   ```html
   <img src="./images/your-new-image.jpg" alt="Description">
   ```

## 📱 Mobile Responsiveness

The website is fully responsive with breakpoints at:
- **Desktop**: 1200px and above
- **Tablet**: 768px - 1199px  
- **Mobile**: 767px and below

## ⚡ Performance Features

- **Single File**: No external dependencies
- **Optimized Images**: Compressed for fast loading
- **Efficient CSS**: Minimal, purpose-built styles
- **Smooth Animations**: Hardware-accelerated transitions
- **Lazy Loading**: Images load as needed

## 🛠️ Technical Details

### Technologies Used
- **HTML5**: Semantic markup
- **CSS3**: Grid, Flexbox, animations
- **Vanilla JavaScript**: No frameworks/libraries
- **Responsive Design**: Mobile-first approach

### Browser Support
- Chrome 70+
- Firefox 65+
- Safari 12+
- Edge 80+
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🔄 Maintenance

### Regular Updates
1. **Content Updates**: Edit text directly in `index.html`
2. **Image Updates**: Replace files in `images/` folder
3. **Style Changes**: Modify CSS variables or styles in `<style>` section

### Adding New Sections
1. Add HTML structure following existing patterns
2. Add corresponding CSS styles
3. Update navigation if needed
4. Test responsiveness

## 📞 Support

For technical support or customization requests:
- **Email**: info@itenasolutions.com
- **Phone**: 700 777 20
- **Address**: 25 Martiou str 21A-2nd floor office 101, Egkomi 2408, Nicosia, Cyprus

## 📜 License

Copyright © 2025 ITEna Solutions. All rights reserved.

---

**Deployment Date**: 2025-06-26  
**Version**: 1.0  
**Author**: MiniMax Agent
