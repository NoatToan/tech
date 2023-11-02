```code 
.
├── README.md
├── index.html
├── package.json
├── public
├── src
│   ├── @shared
│   │   ├── components
│   │   │   ├── atoms
│   │   │   ├── molecules
│   │   │   └── organisms
│   │   ├── hooks
│   │   │   ├── index.ts
│   │   │   ├── useAuthViewModelHook.ts
│   │   │   └── useCheckInViewModelHook.ts
│   │   └── utils
│   │       ├── stringUtils.ts
│   ├── App.css
│   ├── App.tsx
│   ├── assets
│   │   ├── index.ts
│   │   ├── logo.png
│   │   ├── png
│   │   │   └── logo.png
│   │   └── svg
│   │       └── example_user.svg
│   ├── index.css
│   ├── layouts
│   │   ├── AdminLayout
│   │   │   ├── AdminLayout.tsx
│   │   │   ├── components
│   │   │   │   ├── Footer
│   │   │   │   └── Header
│   │   │   └── index.ts
│   │   ├── DefaultLayout
│   │   │   ├── DefaultLayout.tsx
│   │   │   └── index.ts
│   │   └── components
│   │       ├── ContentWrapper
│   │       ├── Header
│   │       └── Sidebar
│   ├── locales
│   │   ├── en
│   │   ├── i18n.ts
│   │   └── jp
│   ├── main.tsx
│   ├── pages
│   │   ├── AuthPage
│   │   │   ├── index.ts
│   │   │   └── screens
│   │   │       ├── ForgotPasswordScreen
│   │   │       │   ├── ForgotPasswordScreen.ts
│   │   │       │   ├── components
│   │   │       │   └── hooks
│   │   │       │       └── useForgotPassword.ts
│   │   │       └── LoginScreen
│   │   │           ├── LoginScreen.ts
│   │   │           ├── components
│   │   │           └── hooks
│   │   │               └── useLogin.ts
│   │   └── CheckInPage
│   │       ├── index.ts
│   │       └── screens
│   │           └── CheckInProcessScreen
│   │               ├── CheckInProcessScreen.ts
│   │               ├── components
│   │               └── hooks
│   ├── store
│   │   ├── index.ts
│   │   ├── slices
│   │   └── store.ts
│   ├── styles
│   │   ├── _fontsClass.scss
│   │   ├── _stylesClass.scss
│   │   ├── _variables.scss
│   │   └── index.scss
│   ├── tests
│   └── vite-env.d.ts
├── tsconfig.json
├── tsconfig.node.json
├── vite.config.ts
└── yarn.lock
```


### React version: ^18.2.0
### Typescript: ^4.9.5

### State management:
1. Redux toolkit (query) ^1.9.3
2. Redux persit ^6.0.0
HTTP client: fetchBaseQuery from redux toolkit 

### Navigation:
1. React router dom ^6.9.0

### Testing:
1. React testing library

### UI, theme Framework: 
1. Antd design ^5.3.1

### Style:
1. Styled component ^6.0.5
2. SCSS module

### Localization: 
1. i18next ^22.4.13

### Code conventions: 
1. ESLint 
2. Prettier

```
Ideally, we follow the MVVM and MVP for project architecture:
Model: Our store reducers slice, slice.api
View: Components in Page folder
ViewModel: Custom hook by actor/model (useAuthViewModelHook). The view model will hold the whole of the business logic of the actor/model
Presentor: The hook which wrap the logic inside the screen, view. Inject the viewmodel logic to achieve the functionality
```


