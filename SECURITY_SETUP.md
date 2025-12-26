# Security Setup for Public Portfolio Repository

## ✅ Recommended: Keep Repository Public + Add EmailJS Security

### Step 1: Enable Domain Restrictions in EmailJS

This prevents others from using your EmailJS service on unauthorized domains.

1. Log in to [EmailJS Dashboard](https://dashboard.emailjs.com/)
2. Go to **"Account"** → **"Security"** (or **"API Keys"**)
3. Find **"Allowed Referrers"** or **"Domain Restrictions"**
4. Add your domain(s):
   - Your portfolio domain (e.g., `yourname.github.io`)
   - `localhost` (for local development)
   - Any other domains where you'll host the site
5. Save the settings

**Result:** Only requests from your specified domains will work, even if someone copies your credentials.

### Step 2: Monitor Your EmailJS Usage

1. Go to **"Account"** → **"Usage"** in EmailJS dashboard
2. Check your email count regularly
3. Set up alerts if you have a paid plan

### Step 3: (Optional) Rotate Keys if Needed

If you suspect abuse:
1. Go to **"Account"** → **"API Keys"**
2. Generate a new Public Key
3. Update it in your code
4. Old key will stop working

---

## Alternative Options

### Option A: Keep Public (Recommended)
✅ **Pros:**
- Shows your coding skills
- Easy to share
- Professional standard

✅ **Security:**
- Use domain restrictions (see above)
- Monitor usage
- EmailJS public keys are designed to be public

### Option B: Keep Private
❌ **Cons:**
- Can't showcase your code easily
- Less professional for a portfolio
- Harder to share with employers

✅ **Use if:**
- You're very concerned about security
- You don't want to set up domain restrictions
- You prefer maximum privacy

### Option C: Public Repo + Environment Variables (Advanced)

If you're using a build system (like Vite, Webpack, etc.):
1. Move credentials to environment variables
2. Add `.env` to `.gitignore`
3. Use build-time replacement

**Note:** This doesn't work for static HTML files without a build step.

---

## Current Security Status

### ✅ Safe to Keep Public:
- EmailJS Public Key (designed to be public)
- Service ID and Template ID (not sensitive on their own)

### ⚠️ Protection Needed:
- **Domain Restrictions** - Prevents unauthorized usage
- **Usage Monitoring** - Catch any abuse early

---

## Quick Security Checklist

- [ ] Enable domain restrictions in EmailJS
- [ ] Add your portfolio domain to allowed list
- [ ] Add `localhost` for development
- [ ] Monitor EmailJS usage monthly
- [ ] Keep EmailJS dashboard password strong
- [ ] Consider 2FA on EmailJS account (if available)

---

## What Happens if Someone Uses Your Credentials?

**With Domain Restrictions Enabled:**
- ❌ They can't use it on their domain
- ✅ Only your domain will work
- ✅ Your quota is protected

**Without Domain Restrictions:**
- ⚠️ They could use your quota
- ⚠️ You might hit the 200 email/month limit
- ⚠️ You'd need to rotate keys

---

## Recommendation

**Keep your repository PUBLIC** and:
1. ✅ Set up domain restrictions (5 minutes)
2. ✅ Monitor usage occasionally
3. ✅ Enjoy showcasing your work!

This is the standard approach for portfolio websites and is perfectly safe with proper configuration.

