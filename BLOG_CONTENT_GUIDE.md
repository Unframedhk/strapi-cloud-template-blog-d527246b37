# Strapi Blog Content Guide

## Quick Start

### 1. Access Strapi Admin
- Go to `http://localhost:1337/admin`
- Log in with your credentials

### 2. Create Content Types (One-time)

**Author:**
- Content Manager → Author → Create new entry
- Fill: Name, Email, Bio (optional), Avatar (optional)
- Save & Publish

**Categories:**
- Content Manager → Category → Create new entry
- Fill: Name, Description (optional), Color (hex code)
- Save & Publish

**Tags:**
- Content Manager → Tag → Create new entry
- Fill: Name, Description (optional)
- Save & Publish

### 3. Create Blog Post

**Required Fields:**
- **Title**: Your post title (max 200 chars)
- **Excerpt**: Brief summary (max 300 chars)
- **Content**: Main content using rich text editor
- **Featured Image**: Upload image (1200x630px recommended)

**SEO Fields:**
- **SEO Title**: For search engines (max 60 chars)
- **SEO Description**: Meta description (max 160 chars)
- **SEO Keywords**: Comma-separated keywords

**Relationships:**
- **Author**: Select from dropdown
- **Category**: Choose category
- **Tags**: Select multiple tags

**Other:**
- **Reading Time**: Set in minutes
- **Featured**: Check to appear on homepage
- **Save & Publish**

## Image Guidelines

**Featured Image:**
- Size: 1200x630px (16:9 ratio)
- Format: JPG, PNG, WebP
- File size: Under 10MB

**Auto-generated sizes:**
- Thumbnail: 245x156px
- Small: 500x320px
- Medium: 750x480px
- Large: 1000x640px

## SEO Best Practices

**Title:** Keep under 60 chars, include keywords
**Description:** Keep under 160 chars, include call-to-action
**Keywords:** Use specific terms, separate with commas

## API Endpoints

```bash
# All published posts
GET /api/blog-posts/published

# Featured posts
GET /api/blog-posts/featured

# Post by slug
GET /api/blog-posts/slug/{slug}

# Posts by category
GET /api/blog-posts/category/{categorySlug}

# Posts by tag
GET /api/blog-posts/tag/{tagSlug}
```

## Troubleshooting

**Image upload issues:** Check file size (< 10MB), format (JPG/PNG/WebP)
**Publishing errors:** Verify all required fields filled
**API issues:** Check Strapi server running

## Quick Commands

```bash
# Start Strapi
npm run develop

# Build for production
npm run build

# Start production
npm run start
```

## Admin URLs

- **Local**: http://localhost:1337/admin
- **Content Manager**: http://localhost:1337/admin/content-manager
- **Media Library**: http://localhost:1337/admin/plugins/upload
