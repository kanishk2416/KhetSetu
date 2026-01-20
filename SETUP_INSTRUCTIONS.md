# KhetSetu - Setup Instructions

## 🚀 Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Environment Variables

Create a `.env.local` file in the root directory:

```env
# Weather API (OpenWeatherMap)
# Get your free API key from: https://openweathermap.org/api
NEXT_PUBLIC_WEATHER_API_KEY=your_openweathermap_api_key_here

# Admin Emails (comma-separated for admin panel access)
NEXT_PUBLIC_ADMIN_EMAILS=admin@example.com,another@example.com
```

### 3. Firebase Configuration

The Firebase configuration is already set up in `src/firebase/config.ts`. Make sure:

1. Firebase Storage is enabled in your Firebase Console
2. Firestore Database is enabled with the security rules from `firestore.rules`
3. Authentication is enabled with:
   - Email/Password provider
   - Google provider (for Google Sign-In)

### 4. Run Development Server

```bash
npm run dev
```

## ✅ Implemented Features

### Core Features
- ✅ Firebase Storage integration for image uploads
- ✅ Real-time weather API (OpenWeatherMap)
- ✅ Google OAuth authentication
- ✅ Forms for creating listings (crops, equipment, forum posts)
- ✅ AI results persistence to Firestore
- ✅ Search functionality
- ✅ Pagination for large lists
- ✅ Loading states and error boundaries
- ✅ Admin panel for managing experts and tags

### Pages Updated
- ✅ Market page (Firestore, search, pagination)
- ✅ Dashboard (weather API)
- ✅ Login/Signup (Google OAuth)
- ✅ Recommendations (persist results)
- ✅ Diagnostics (Storage upload, persist results)
- ✅ Admin panel

## 📝 Remaining Updates (Optional)

The following pages can be updated following the same pattern as the Market page:

### Equipment Page
- Replace static data with Firestore queries
- Use `CreateEquipmentForm` component
- Add search and pagination

### Community Page  
- Replace static data with Firestore queries
- Use `CreateForumPostForm` component
- Add search and pagination
- Update timestamp handling for real-time data

### Experts Page
- Replace static data with Firestore queries from `/expertProfiles`

These follow the same pattern as the Market page implementation.

## 🔧 Firestore Collections

Make sure these collections exist in your Firestore:

### Public Collections
- `cropListings` - Marketplace crop listings
- `equipment` - Equipment rentals/sales
- `forumPosts` - Community forum posts
- `expertProfiles` - Agricultural experts
- `tags` - Forum tags

### User Collections (nested under `/users/{userId}`)
- `cropRecommendations` - User's crop recommendations
- `pestDiseaseDetections` - User's pest detection results
- `cropHealthMetrics` - User's crop health data

## 🔐 Admin Access

To access the admin panel:
1. Set `NEXT_PUBLIC_ADMIN_EMAILS` in `.env.local`
2. Sign in with an email listed in that variable
3. Access `/admin` route from the sidebar

## 📦 Key Dependencies

- Next.js 15
- Firebase 11
- Genkit AI (Google Gemini)
- Tailwind CSS + shadcn/ui
- React Hook Form + Zod
- Recharts (for charts)

## 🐛 Troubleshooting

### Weather API Not Working
- Check if `NEXT_PUBLIC_WEATHER_API_KEY` is set
- Verify the API key is valid
- Check browser console for errors

### Image Upload Fails
- Verify Firebase Storage is enabled
- Check Storage security rules
- Ensure user is authenticated

### Firestore Errors
- Verify Firestore security rules match `firestore.rules`
- Check browser console for permission errors
- Ensure collections exist or are created on first write

## 📚 Documentation

See `IMPLEMENTATION_SUMMARY.md` for detailed implementation notes.
