# 🟩 Story: Login Frontend UI (Google Button)

**As a** user  
**I want to** see a Google login button on the login screen  
**So that** I can sign in to PostStash using my Google account

---

## ✅ Acceptance Criteria

### 1️⃣ Visual Elements 

- Given that I have opened PostStash mobile app  
- When the login screen is rendered  
- Then I should be able to see the following:
  - A responsive screen with a gradient background
  - Text Logo "PostStash" centered on the page
  - A Google login button at the bottom of the page
  - Button CTA "Continue With Google"
  - The Google icon (`<FaGoogle />`)
  - Terms and conditions text beneath the google button
    
 ---

### 2️⃣ Button Behavior and Navigation to Google

- When I tap the Google button
- Then I should be able to button should be **briefly disabled** to prevent multiple taps  
- Then I should be able to navigate to the google sign in page

---

### 3️⃣ --- Successful Login Flow

- Given that I am on the google sign in page
- When I log-in sucessfully
- Then I should be navigated back to the login screen loading state

---

### 4️⃣ Loading State (After Returning From Google)

- Given that I am navigated back to the login screen 
- When I view the Google button
- Then I should see a **loading indicator** while the app:
  - Verifies my session
  - Optionally fetches additional data
- The loading indicator should:
  - Show that the app is actively processing
  - Disappear once verification is complete
- Given that the session has been verified
- When I
- Then I should be navigated to the onboarding screen
 
---

### 5️⃣ Failed Login or Cancelled Flow

- Given that I am on the google sign in page
- When I log-in unsuccessfully
- Then I should be able to view an error message 

---

## 🛠️ Component & Implementation

- **Screen:** `Login.jsx`
- **Button:** BorderButton component with `icon={<FaGoogle />}` and `text="Google"`
- **Event:** Triggers `handleSignIn()` on press
- **Flow:** Integrated with Supabase OAuth using the `supabase.auth.signInWithOAuth()` method

- ## 🖼️ UI Layout Details

- **Background:** Fullscreen gradient color #...
- **Logo Text:** `"PostStash"` rendered as an `<Animated.Text>` with `styles.textLogo`
  - Font: Custom, bold
  - Size: 24+
  - Color: White or high-contrast over gradient
- **Google Button:**
  - Full-width button with `icon={<FaGoogle />}` and `text="Google"`
  - Placed below the logo with adequate spacing
  - Uses the `BorderButton` reusable component
- **Spacing & Flex:** Ensures logo and button are vertically aligned and responsive
