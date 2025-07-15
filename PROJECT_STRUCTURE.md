# Kutbul Zaman - Project Structure

## Overview

Bu proje, Kutbul Zaman adlı çok sistemli platform için geliştirilmiş ortak kod yapısına sahiptir. Tüm alt sistemler aynı auth sistemi, UI framework ve routing yapısını kullanır.

## 🏗️ Architecture

### 1. Global Auth System ✅

- **Context**: `src/auth/AuthContext.tsx` - Global auth state management
- **Types**: `src/auth/types.ts` - User, roles, and auth type definitions
- **Storage**: localStorage'da token ve user bilgileri global saklanır
- **Roles**: `user`, `admin`, `mlm`, `psychologist`, `merchant`

### 2. Common UI System ✅

- **Design System**: Navy (#0D1B2A) + Gold (#FFD700) color scheme
- **Components**: `src/components/` - Reusable UI components
- **Styles**: `src/styles/global.css` - Global CSS with design system
- **Font**: Inter, sans-serif across all elements
- **Animations**: Page transitions, button hover effects, soft shadows

### 3. Central Portal Routing ✅

```
/portal        → Central system selector (role-based access)
/panel         → Common user panel
/mlm           → Network system (MLM, Admin only)
/shop          → E-commerce (Merchant, User, Admin)
/self          → Personal development (Psychologist, User, Admin)
/admin         → System administration (Admin only)
```

### 4. Shared Context & Services ✅

- **Auth Context**: Global authentication state
- **API Service**: `src/services/api.ts` - Centralized API calls
- **Utils**: `src/utils/` - Shared utility functions
- **Constants**: `src/constants/` - App-wide constants

### 5. Login Protection ✅

- **ProtectedRoute**: `src/components/ProtectedRoute.tsx`
- **Auth Guards**: Automatic redirect to `/login` if not authenticated
- **Role Checks**: Role-based access control for system pages
- **Redirect Flow**: After login, redirects to intended page or portal

## 🔧 Environment Configuration

```env
VITE_API_URL=https://api.kutbulzaman.com
VITE_APP_NAME=Kutbul Zaman
VITE_SYSTEM_MODE=development  # mlm | ecommerce | self | admin | development
```

## 📁 File Structure

```
src/
├── auth/                 # Authentication system
│   ├── AuthContext.tsx   # Global auth context
│   ├── types.ts         # Auth type definitions
│   └── RoleGuard.tsx    # Role-based components
├── components/          # Reusable UI components
│   ├── Header.tsx       # Navigation header
│   ├── Footer.tsx       # Common footer
│   ├── ProtectedRoute.tsx # Auth route protection
│   └── PageTransition.tsx # Page animation wrapper
├── pages/               # Application pages
│   ├── Index.tsx        # Homepage
│   ├── Login.tsx        # Login page
│   ├── Portal.tsx       # System selector
│   ├── Panel.tsx        # User panel
│   ├── MLM.tsx          # Network system
│   ├── Shop.tsx         # E-commerce
│   ├── Self.tsx         # Personal development
│   └── Admin.tsx        # Administration
├── services/            # API and external services
│   ├── api.ts           # Centralized API service
│   ├── auth.ts          # Authentication service
│   └── whatsapp.ts      # WhatsApp integration
├── utils/               # Utility functions
│   ├── auth-config.ts   # Auth configuration
│   ├── validation.ts    # Form validation
│   └── cn.ts            # Class name utilities
├── layouts/             # Page layout components
│   ├── MainLayout.tsx   # Primary layout
│   └── AuthLayout.tsx   # Auth pages layout
├── styles/              # Styling
│   └── global.css       # Global styles & design system
└── constants/           # App constants
    └── index.ts         # Routes, config, etc.
```

## 🛡️ Security Features

1. **JWT Token Management**: Automatic token validation and refresh
2. **Role-Based Access**: System access based on user roles
3. **Route Protection**: Automatic login redirects for protected routes
4. **Session Persistence**: User session maintained across browser restarts
5. **Error Boundaries**: Graceful error handling throughout the app

## 🎨 Design System

### Colors

- **Primary**: Navy Blue (#0D1B2A)
- **Secondary**: Gold (#FFD700)
- **Background**: White/Gray gradients
- **Text**: Navy for headings, gray for body

### Components

- **Buttons**: Rounded corners, soft shadows, hover animations
- **Cards**: Elevated design with subtle shadows
- **Inputs**: Rounded borders, focus states with gold accent
- **Navigation**: Clean, role-based menu items

### Animations

- **Page Transitions**: Fade-in effects on route changes
- **Hover Effects**: Smooth scale and shadow transitions
- **Loading States**: Spinner animations during async operations

## 🚀 Usage Guidelines

### Adding New Systems

1. Create page in `src/pages/NewSystem.tsx`
2. Add route to `src/constants/index.ts`
3. Update `src/utils/auth-config.ts` with role permissions
4. Wrap page content with `<ProtectedRoute requiredRoles={["role"]}>`
5. Add system card to Portal page

### Authentication Integration

```tsx
import { useAuth } from "../auth/AuthContext";
import { ProtectedRoute } from "../components/ProtectedRoute";

// In component
const { user, isAuthenticated, logout } = useAuth();

// Route protection
<ProtectedRoute requiredRoles={["admin", "user"]}>
  <YourComponent />
</ProtectedRoute>;
```

### API Integration

```tsx
import { apiService } from "../services/api";

// Make API calls
await apiService.submitContactForm(formData);
```

This structure ensures consistency across all Kutbul Zaman subsystems while maintaining security, performance, and user experience standards.
