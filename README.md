# Annapurna Tiffin Service - Complete Production System

**Version 1.0 - Production Ready**

A complete, scalable platform for Annapurna Tiffin Service featuring a Next.js website, React Native mobile apps (iOS/Android), admin dashboard, and Firebase backend.

## Features

✅ **Website (Next.js)**
- Phone OTP authentication (Firebase)
- About Us, offers, contact details, app download links
- Feedback & order inquiry forms
- Mobile-first responsive design
- Firebase Analytics event tracking

✅ **Admin Dashboard**
- Secure email/password login
- Offers CRUD operations
- Customer list with CSV export
- Analytics dashboard (users, feedback, inquiries, engagement)
- Push notification sender (Firebase Cloud Messaging)

✅ **Mobile Apps (iOS + Android via Expo)**
- Phone OTP authentication
- Profile management
- Home screen with offers & tiffin details
- Call/WhatsApp quick actions
- Feedback submission
- Push notifications

✅ **Firebase Backend**
- Cloud Functions for automation
- Phone authentication
- Firestore database with security rules
- Cloud Messaging (FCM) for push notifications
- Analytics tracking
- CSV exports

✅ **Analytics Tracking**
- `page_view`, `otp_requested`, `otp_verified`
- `contact_click`, `whatsapp_click`
- `app_download_click`
- `feedback_submitted`, `order_inquiry_submitted`
- "Tried to connect" = contact_click OR whatsapp_click

## Tech Stack

- **Frontend:** Next.js 14, React, TypeScript
- **Mobile:** React Native (Expo)
- **Backend:** Firebase (Auth, Firestore, Cloud Functions, Messaging)
- **Analytics:** Firebase Analytics / Google Analytics 4
- **Hosting:** Firebase Hosting
- **Form Validation:** React Hook Form, Yup

## Project Structure

```
annapurna-tiffin-service/
├── website/                 # Next.js web application
├── admin-dashboard/         # Admin React app
├── mobile-app/              # Expo React Native app
├── backend/functions/       # Firebase Cloud Functions
├── README.md
└── .gitignore
```

## Quick Start

### Prerequisites
- Node.js 16+ & npm/yarn
- Firebase CLI (`npm install -g firebase-tools`)
- Expo CLI (`npm install -g expo-cli`)

### 1. Firebase Setup

```bash
# Create Firebase project
1. Go to firebase.google.com
2. Create new project: "annapurna-tiffin-prod"
3. Enable: Auth (Phone), Firestore, Storage, Cloud Functions, Messaging, Analytics
4. Copy config to .env files
```

### 2. Installation

```bash
# Clone and install
git clone https://github.com/aryan21Genz/annapurna-tiffin-service.git
cd annapurna-tiffin-service
npm run setup
```

### 3. Development

```bash
# Website (localhost:3000)
npm run dev:website

# Admin Dashboard (localhost:3001)
npm run dev:admin

# Mobile App (Expo)
npm run dev:mobile
```

### 4. Deployment

```bash
# Deploy to Firebase
npm run deploy

# Build Android APK/AAB (Expo)
cd mobile-app
npx eas build -p android --profile production

# Build iOS IPA (Expo)
npx eas build -p ios --profile production
```

## Configuration

### .env Files

**website/.env.local**
```
NEXT_PUBLIC_FIREBASE_API_KEY=...
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=...
NEXT_PUBLIC_FIREBASE_PROJECT_ID=...
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=...
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=...
NEXT_PUBLIC_FIREBASE_APP_ID=...
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=...
```

## Database Schema

**Firestore Collections:**
- `users` - User profiles & phone numbers
- `offers` - Tiffin service offers
- `feedback` - Customer feedback
- `orderInquiries` - Order inquiries
- `events` - Analytics events
- `userDevices` - FCM device tokens

## Security

✅ Production-ready Firestore security rules  
✅ Phone OTP verification  
✅ Admin role-based access control  
✅ Environment variables for sensitive data  
✅ HTTPS-only API calls  

## Testing

**Test OTP (No SMS charges):**
1. Firebase Console > Authentication > Phone
2. Add test number: `+91 9999999999`
3. Test code: `123456`

**Demo Admin:**
- Email: `admin@annapurna.com`
- Password: `Admin@12345`

## Publishing

### Play Store (Android)
- Requirement: Google Play Console account ($25 one-time)
- Build AAB via EAS
- Upload to Play Console
- Review time: 3-24 hours

### App Store (iOS)
- Requirement: Apple Developer account ($99/year)
- Build IPA via EAS
- Upload via TestFlight
- Review time: 24-48 hours

## Costs

**Monthly:**
- Firebase: ~$10 (mostly free tier)
- Hosting: Free (Firebase)
- Functions: Free tier
- Total: Minimal

**One-time:**
- Play Store: $25
- App Store: $99/year

## Troubleshooting

**OTP not sending:**
- Check reCAPTCHA configuration
- Verify Firebase Auth domain whitelist
- Check SMS quota

**Build fails:**
```bash
rm -rf node_modules .expo
npm install
npm install -g expo@latest
```

**App crashes:**
- Verify Firebase config in .env
- Check Firestore rules allow access
- Check browser console for errors

## Next Steps

1. ✅ Create Firebase project
2. ✅ Add Firebase config to .env files
3. ✅ Install dependencies: `npm run setup`
4. ✅ Test locally: `npm run dev:website`
5. ✅ Deploy backend: `firebase deploy --only functions`
6. ✅ Deploy website: `npm run deploy`
7. ✅ Build mobile apps: `eas build -p android` & `eas build -p ios`
8. ✅ Publish to stores

## Resources

- [Firebase Documentation](https://firebase.google.com/docs)
- [Next.js Documentation](https://nextjs.org/docs)
- [React Native Docs](https://reactnative.dev/)
- [Expo Documentation](https://docs.expo.dev/)

## License

MIT

## Support

For issues or questions, contact: admin@annapurna.com

---

**Made with ❤️ for Annapurna Tiffin Service**
