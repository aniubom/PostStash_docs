# 🟩 Story: Login Frontend UI (Google Button)

**As a** user  
**I want to** see a Google login button on the login screen  
**So that** I can sign in to PostStash using my Google account

---

## ✅ Acceptance Criteria

- Given the user has opened the PostStash mobile app  
- When the login screen is rendered  
- Then I shhould be able to see the following:
  - a responsive screen with a gradeint background
  - Text Logo titled "PostStash"
  -
  - The Google icon (`<FaGoogle />`)
  - The label: "Google"
  - A styled border button matching app design

- When the user taps the Google button  
- Then the app should trigger the `handleSignIn()` function

- If the sign-in is successful  
- Then the user should be navigated to the onboarding screen

- If the sign-in fails  
- Then a toast or error message should be displayed

---

## 🛠️ Component & Implementation

- **Screen:** `Login.jsx`
- **Button:** BorderButton component with `icon={<FaGoogle />}` and `text="Google"`
- **Event:** Triggers `handleSignIn()` on press
- **Flow:** Integrated with Supabase OAuth using the `supabase.auth.signInWithOAuth()` method
