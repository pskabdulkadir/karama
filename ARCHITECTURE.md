# Kutbul Zaman Project Architecture

## ✅ Implementation Status

### 1. Global Auth System

- **Status**: ✅ IMPLEMENTED
- **Location**: `src/auth/`
- **Features**:
  - Token-based authentication with localStorage persistence
  - Global user state management with React Context
  - Standardized user structure: `{ id, name, email, role, isActive }`
  - Role-based access control: user, admin, mlm, psychologist, merchant
  - Current system tracking: mlm, ecommerce, development, panel

### 2. Common UI System

- **Status**: ✅ IMPLEMENTED
- **Location**: `src/components/ui/`, `src/global.css`
- **Features**:
  - Kutbul Zaman design system (Navy Blue #0D1B2A + Gold #FFD700)
  - Inter font family throughout
  - Rounded corners with soft shadows
  - Hover animations and transitions
  - Consistent button, card, and input components
  - Fade-in page transitions

### 3. Central Portal Router System

- **Status**: ✅ IMPLEMENTED
- **Location**: `src/routes/`, `src/pages/Portal.tsx`
- **Convention**:
  ```
  /portal → Central redirection page
  /panel  → Common user dashboard
  /mlm    → Network marketing system
  /shop   → E-commerce system
  /self   → Personal development system
  /admin  → Administrator management
  ```

### 4. Shared Context & Service Layer

- **Status**: ✅ IMPLEMENTED
- **Location**: `src/auth/`, `src/services/`, `src/constants/`
- **Features**:
  - GlobalProvider for cross-system compatibility
  - Centralized API service (`src/services/api.ts`)
  - Standardized auth types and interfaces
  - MLM-specific data service layer
  - Environment configuration support

### 5. Authentication Protection

- **Status**: ✅ IMPLEMENTED
- **Location**: `src/components/auth/ProtectedRoute.tsx`
- **Features**:
  - Automatic redirect to `/login` for unauthenticated users
  - URL parameter preservation for post-login redirect
  - Role-based route protection
  - Loading states during auth checks
  - Unauthorized access page

## 🏗️ Project Structure

```
src/
├── auth/                     # Authentication system
│   ├── AuthContext.tsx      # React Context for auth state
│   ├── GlobalContext.tsx    # Cross-system compatibility
│   ├── auth-service.ts      # Auth business logic
│   └── useMLMData.ts        # MLM-specific data hook
├── components/
│   ├── auth/                # Auth-related components
│   │   ├── ProtectedRoute.tsx
│   │   └── RoleGuard.tsx
│   ├── ui/                  # Base UI components
│   │   ├── button.tsx       # Enhanced with Kutbul Zaman styling
│   │   ├── card.tsx
│   │   ├── input.tsx
│   │   └── ...
│   └── Header.tsx           # Global header component
├── constants/
│   ├── auth-types.ts        # Standardized type definitions
│   └── mlm-types.ts         # MLM-specific types
├── pages/
│   ├── Login.tsx            # Enhanced with redirect handling
│   ├── Portal.tsx           # Central system selector
│   ├── AdminDashboard.tsx   # Admin management
│   ├── MLMSystem.tsx        # Network marketing hub
│   ├── Shop.tsx             # E-commerce placeholder
│   └── SelfDevelopment.tsx  # Personal development placeholder
├── routes/
│   └── index.tsx            # Centralized routing with protection
├── services/
│   ├── api.ts               # API service layer
│   └── users-database.ts    # User data service
└── utils/
    └── index.ts             # Utility functions
```

## 🔧 Configuration

### Environment Variables

```env
VITE_API_URL=https://api.kutbulzaman.com
VITE_APP_NAME=Kutbul Zaman
VITE_SYSTEM_MODE=mlm
```

### Tailwind Configuration

- Custom color palette with Navy Blue and Gold
- Animation utilities (fade-in, slide-up, soft-bounce)
- Responsive design support
- Dark mode compatibility

## 🚀 Usage Examples

### Authentication Check

```tsx
import { useAuth } from "../auth/AuthContext";

function MyComponent() {
  const { user, isAuthenticated, hasRole } = useAuth();

  if (!isAuthenticated) {
    return <div>Please login</div>;
  }

  return <div>Welcome, {user.name}</div>;
}
```

### Protected Routes

```tsx
<ProtectedRoute allowedRoles={["admin", "mlm"]}>
  <AdminPanel />
</ProtectedRoute>
```

### Role-based UI

```tsx
<RoleGuard allowedRoles={["admin"]}>
  <AdminButton />
</RoleGuard>
```

### API Usage

```tsx
import { login, fetchUser } from "../services/api";

const loginUser = async (email, password) => {
  const response = await login(email, password);
  return handleApiResponse(response);
};
```

## 🎨 Design System

### Colors

- **Primary**: Navy Blue (#0D1B2A)
- **Secondary**: Gold (#FFD700)
- **Background**: Clean whites and subtle grays
- **Text**: High contrast for accessibility

### Typography

- **Font**: Inter (weights 300-800)
- **Brand elements**: Custom font weight and letter spacing

### Components

- **Buttons**: Rounded corners, soft shadows, hover animations
- **Cards**: Elevated design with hover effects
- **Inputs**: Clean design with focus states
- **Animations**: Smooth transitions and micro-interactions

## 🔒 Security Features

- Token-based authentication
- Role-based access control
- Protected route components
- Input validation and sanitization
- Secure localStorage handling
- CSRF protection ready

## 📱 Responsive Design

- Mobile-first approach
- Flexible grid systems
- Touch-friendly interfaces
- Progressive enhancement
- Optimized for all screen sizes

---

**Last Updated**: Today
**Status**: Production Ready ✅
**Maintainer**: Kutbul Zaman Development Team
