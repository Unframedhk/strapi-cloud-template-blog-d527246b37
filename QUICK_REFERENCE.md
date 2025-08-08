# Strapi Blog Quick Reference

## Quick Checklist

### 1. Create Author (One-time)
- [ ] Content Manager → Author → Create new entry
- [ ] Fill: Name, Email, Bio (optional), Avatar (optional)
- [ ] Save & Publish

### 2. Create Categories (One-time)
- [ ] Content Manager → Category → Create new entry
- [ ] Fill: Name, Description (optional), Color (hex code)
- [ ] Save & Publish

### 3. Create Tags (One-time)
- [ ] Content Manager → Tag → Create new entry
- [ ] Fill: Name, Description (optional)
- [ ] Save & Publish

### 4. Create Blog Post
- [ ] Content Manager → Blog Post → Create new entry
- [ ] Fill required fields: Title, Excerpt, Content, Featured Image
- [ ] Set SEO: Title, Description, Keywords
- [ ] Select: Author, Category, Tags
- [ ] Set Reading Time, Mark Featured (optional)
- [ ] Save & Publish

## Image Requirements

**Featured Image:**
- Size: 1200x630px (16:9 ratio)
- Format: JPG, PNG, WebP
- File size: Under 10MB

**Auto-generated:**
- Thumbnail: 245x156px
- Small: 500x320px
- Medium: 750x480px
- Large: 1000x640px

## SEO Guidelines

**Title:** Under 60 chars, include keywords
**Description:** Under 160 chars, include call-to-action
**Keywords:** Specific terms, comma-separated

## API Endpoints

```bash
GET /api/blog-posts/published    # All published posts
GET /api/blog-posts/featured     # Featured posts
GET /api/blog-posts/slug/{slug}  # Post by slug
GET /api/blog-posts/category/{categorySlug}  # By category
GET /api/blog-posts/tag/{tagSlug}  # By tag
```

## Quick Commands

```bash
npm run develop  # Start Strapi
npm run build    # Build for production
npm run start    # Start production
```

## Admin URLs

- **Admin Panel**: http://localhost:1337/admin
- **Content Manager**: http://localhost:1337/admin/content-manager
- **Media Library**: http://localhost:1337/admin/plugins/upload

## Troubleshooting

**Image upload:** Check size (< 10MB), format (JPG/PNG/WebP)
**Publishing:** Verify all required fields filled
**API:** Check Strapi server running
