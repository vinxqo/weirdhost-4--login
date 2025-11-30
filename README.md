# Run Time Adder Script Instructions

This project supports two login methods to access Pterodactyl or related systems:

1. **Login using Cookie**  
2. **Login using email and password**

---

## Method 1: Login Using Cookie

### Applicable Scenarios
- You need to maintain a long-term session to avoid frequent logins.
- You already have a valid cookie that can be reused.

### Steps to Obtain the Cookie
1. Log in to the target website (such as the Pterodactyl panel).
2. Open the browser Developer Tools (press F12 or right-click the page and select Inspect).
3. Switch to the Application tab.
4. In the left panel, find the Cookies section and select the current site.
5. Locate the cookie related to login (such as session, auth_token, etc.).
6. Copy the cookie value.

### Configure in GitHub Secrets
1. Open your GitHub repository and go to **Settings > Secrets and variables > Actions**。
2. 点击 **New repository secret**。
3. Create a secret named REMEMBER_WEB_COOKIE and paste the copied cookie value into it.

### Benefits
- Each workflow run will automatically use this cookie to log in without re-entering your account and password.

---

## Method 2: Login Using Email and Password

If you don’t have a valid cookie, you can log in using an email and password.

### Configure in GitHub Secrets
1. Open your GitHub repository and go to **Settings > Secrets and variables > Actions**。
2. 点击 **New repository secret**。
3. Create the following two secrets：
   - `PTERODACTYL_EMAIL`：Your Pterodactyl account email.
   - `PTERODACTYL_PASSWORD`：Your Pterodactyl account password.

### Benefits
- No need to manually obtain a cookie; simply log in using your account credentials.

---

## Recommended Approach
- **Prefer using Cookie**：More stable and won’t fail due to password changes.  
- **Use email/password as backup**：When the cookie expires, you can use email and password to log in again.  

---
