# Blog CMS - Strapi

A headless CMS for managing blog content across multiple projects (replicaCam, 1ms, space-website).

## 🚀 Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Start Development Server
```bash
npm run develop
```

The admin panel will be available at: http://localhost:1337/admin

## 📝 Content Types

### Blog Post
- **Title**: Required, unique, max 200 characters
- **Slug**: Auto-generated from title, unique
- **Excerpt**: Required, max 300 characters
- **Content**: Rich text editor
- **Featured Image**: Required, image upload
- **Published At**: Auto-set when published
- **Reading Time**: Integer, default 0
- **SEO Title**: Optional, max 60 characters
- **SEO Description**: Optional, max 160 characters
- **SEO Keywords**: Optional
- **Featured**: Boolean, default false
- **Author**: Relation to Author
- **Category**: Relation to Category
- **Tags**: Many-to-many relation with Tags

### Author
- **Name**: Required, unique
- **Email**: Required, unique, email format
- **Bio**: Optional, max 500 characters
- **Avatar**: Optional, image upload
- **Social Links**: JSON field for social media URLs

### Category
- **Name**: Required, unique, max 100 characters
- **Slug**: Auto-generated from name, unique
- **Description**: Optional, max 500 characters
- **Color**: Optional, hex color code

### Tag
- **Name**: Required, unique, max 50 characters
- **Slug**: Auto-generated from name, unique
- **Description**: Optional, max 200 characters

## 🔌 API Endpoints

### Standard Strapi Endpoints
- `GET /api/blog-posts` - Get all blog posts
- `GET /api/blog-posts/:id` - Get specific blog post
- `GET /api/authors` - Get all authors
- `GET /api/categories` - Get all categories
- `GET /api/tags` - Get all tags

### Custom Endpoints
- `GET /api/blog-posts/published` - Get all published posts with full relations
- `GET /api/blog-posts/slug/:slug` - Get post by slug with full relations
- `GET /api/blog-posts/slugs` - Get all slugs for static generation
- `GET /api/blog-posts/featured` - Get featured posts (limit 3)
- `GET /api/blog-posts/category/:categorySlug` - Get posts by category
- `GET /api/blog-posts/tag/:tagSlug` - Get posts by tag

## 🎯 Frontend Integration

### Environment Variables
Add to your frontend project's `.env.local`:

```env
# Development
NEXT_PUBLIC_BLOG_API_URL=http://localhost:1337/api

# Production (update with your deployed Strapi URL)
NEXT_PUBLIC_BLOG_API_URL=https://your-strapi-blog-cms.com/api
```

### Blog Service Usage
```typescript
import blogService from '../utils/blogService';

// Get all posts
const posts = await blogService.getAllPosts();

// Get featured posts
const featured = await blogService.getFeaturedPosts();

// Get post by slug
const post = await blogService.getPostBySlug('my-post-slug');

// Get all slugs for static generation
const slugs = await blogService.getAllSlugs();
```

## 📱 Projects Integration

### replicaCam
- Blog section on main page
- `/blog` - Blog list page
- `/blog/[slug]` - Individual blog post pages
- Static generation with `generateStaticParams`

### 1ms
- Blog section on main page
- `/blog` - Blog list page
- `/blog/[slug]` - Individual blog post pages
- Static generation with `generateStaticParams`

### space-website
- Blog section on main page
- `/blog` - Blog list page
- `/blog/[slug]` - Individual blog post pages
- Static generation with `generateStaticParams`

## 🔧 Configuration

### Strapi Configuration Files
- `config/server.js` - Server configuration
- `config/admin.js` - Admin panel configuration
- `config/database.js` - Database configuration
- `config/plugins.js` - Plugin configuration

### Environment Variables
Create `.env` file in the root directory:

```env
HOST=0.0.0.0
PORT=1337
APP_KEYS=myKeyA,myKeyB,myKeyC,myKeyD
API_TOKEN_SALT=myApiTokenSalt
ADMIN_JWT_SECRET=myAdminJwtSecret
JWT_SECRET=myJwtSecret
```

## 🚀 Deployment

### Local Development
```bash
npm run develop
```

### Production Build
```bash
npm run build
npm run start
```

### Docker Deployment
```bash
docker build -t blog-cms .
docker run -p 1337:1337 blog-cms
```

## 📊 Content Management

### Creating Blog Posts
1. Go to http://localhost:1337/admin
2. Navigate to "Content Manager" → "Blog Post"
3. Click "Create new entry"
4. Fill in required fields:
   - Title
   - Excerpt
   - Content (use rich text editor)
   - Upload featured image
   - Select author
   - Select category
   - Add tags
   - Set reading time
   - Add SEO fields
5. Click "Save" then "Publish"

### Managing Authors
1. Navigate to "Content Manager" → "Author"
2. Create author entries with:
   - Name
   - Email
   - Bio
   - Avatar image
   - Social links (JSON format)

### Managing Categories
1. Navigate to "Content Manager" → "Category"
2. Create categories with:
   - Name
   - Description
   - Color (hex code)

### Managing Tags
1. Navigate to "Content Manager" → "Tag"
2. Create tags with:
   - Name
   - Description

## 🔍 SEO Optimization

### Meta Tags
Each blog post includes:
- SEO Title
- SEO Description
- SEO Keywords
- Open Graph tags
- Twitter Card tags

### Static Generation
- All blog posts are pre-rendered at build time
- SEO-friendly URLs with slugs
- Fast loading times
- Search engine optimized

## 🛠️ Troubleshooting

### Common Issues

1. **API Connection Error**
   - Check if Strapi server is running
   - Verify API URL in frontend configuration
   - Check CORS settings

2. **Image Loading Issues**
   - Ensure images are uploaded to Strapi
   - Check image URL formatting
   - Verify media library permissions

3. **Static Generation Errors**
   - Check if all required fields are filled
   - Verify slug generation
   - Check for duplicate slugs

### Debug Mode
Enable debug logging in Strapi:
```bash
NODE_ENV=development DEBUG=strapi:* npm run develop
```

## 📚 Additional Resources

- [Strapi Documentation](https://docs.strapi.io/)
- [Next.js Static Generation](https://nextjs.org/docs/basic-features/data-fetching/get-static-props)
- [SEO Best Practices](https://developers.google.com/search/docs/advanced/guidelines/overview)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.
