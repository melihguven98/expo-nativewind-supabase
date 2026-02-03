# Expo Router Patterns

## File Structure
```
app/
├── _layout.tsx      # Root layout
├── index.tsx        # Home (/)
├── (tabs)/          # Tab group
│   ├── _layout.tsx  # Tab layout
│   ├── home.tsx     # /home
│   └── profile.tsx  # /profile
├── (auth)/          # Auth group
│   ├── login.tsx    # /login
│   └── register.tsx # /register
└── [id].tsx         # Dynamic /:id
```

## Navigation
```typescript
import { router } from 'expo-router';

// Push
router.push('/profile');
router.push({ pathname: '/user/[id]', params: { id: '123' } });

// Replace
router.replace('/home');

// Back
router.back();
```
