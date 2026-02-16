# 3x5 Workout Tracker

A progressive strength training app similar to StrongLifts 5x5, but customizable for both 3x5 and 5x5 programs.

## Features

- **Onboarding Flow**: Set your starting weights for each exercise
- **Progressive Overload**: Automatically suggests +5 lbs when you complete all sets
- **Deload System**: Tracks failures and suggests -10% weight after 3 consecutive failures
- **A/B Workout Split**: Alternates between two full-body workouts
- **Warmup Checklist**: Guided warmup routine before each workout
- **Rest Timer**: 3-minute countdown timer between sets
- **Workout History**: View all past workouts with detailed set/rep data
- **Data Export**: Export your workout history to CSV
- **Offline Capable**: Works without internet connection (PWA)
- **Mobile Optimized**: Designed for mobile devices with touch-friendly UI

## Workout Programs

### Workout A
- Squat: 3x5 or 5x5
- Bench Press: 3x5 or 5x5
- Barbell Row: 3x5 or 5x5

### Workout B
- Squat: 3x5 or 5x5
- Overhead Press: 3x5 or 5x5
- Deadlift: 3x5 or 5x5

## Deployment Options

### Option 1: Web App (Easiest)

The app works as a Progressive Web App (PWA) and can be installed on Android devices directly from the browser.

#### Deployment Steps:

1. **Using GitHub Pages** (Free):
   ```bash
   # Initialize git if not already done
   git init
   git add .
   git commit -m "Initial commit"

   # Create a new repository on GitHub
   # Then push:
   git remote add origin https://github.com/yourusername/workout-3x5-app.git
   git branch -M main
   git push -u origin main

   # Enable GitHub Pages in repository settings
   # Set source to main branch, / (root)
   ```

   Your app will be available at: `https://yourusername.github.io/workout-3x5-app/`

2. **Using Netlify** (Free, easier):
   - Drag and drop the entire folder to [Netlify Drop](https://app.netlify.com/drop)
   - Get instant deployment with HTTPS
   - Or connect your GitHub repo for automatic deployments

3. **Using Vercel** (Free):
   - Install Vercel CLI: `npm install -g vercel`
   - Run: `vercel`
   - Follow the prompts

#### Installing on Android:

1. Open the deployed URL in Chrome on your Android device
2. Tap the menu (⋮) and select "Install app" or "Add to Home Screen"
3. The app will install like a native app
4. Works offline after first load

### Option 2: Android APK (Advanced)

To create a native APK using Capacitor:

#### Prerequisites:
- Node.js installed
- Android Studio installed
- Java JDK 11 or higher

#### Steps:

1. **Initialize Capacitor**:
   ```bash
   npm init -y
   npm install @capacitor/core @capacitor/cli @capacitor/android
   npx cap init "3x5 Workout" "com.yourname.workout3x5" --web-dir .
   ```

2. **Add Android Platform**:
   ```bash
   npx cap add android
   ```

3. **Open in Android Studio**:
   ```bash
   npx cap open android
   ```

4. **Build APK**:
   - In Android Studio: Build → Build Bundle(s) / APK(s) → Build APK(s)
   - APK will be in: `android/app/build/outputs/apk/debug/app-debug.apk`

5. **Install on Phone**:
   - Transfer APK to phone
   - Enable "Install from unknown sources" in settings
   - Install the APK

### Option 3: Cordova (Alternative)

```bash
npm install -g cordova
cordova create 3x5Workout com.yourname.workout3x5 "3x5 Workout"
cd 3x5Workout
# Copy index.html and other files to www/ directory
cordova platform add android
cordova build android
```

## Local Development

Simply open `index.html` in a web browser. For best results, use a local server:

```bash
# Python 3
python -m http.server 8000

# Or Node.js
npx serve
```

Then open `http://localhost:8000`

## Data Storage

All data is stored locally in browser's localStorage:
- Workout history
- Starting weights
- Settings (3x5 vs 5x5, auto-fill preferences)
- Failure tracking for deloads

**Important**:
- Data persists across sessions
- Export regularly using the "Export Data" button
- Data is not synced across devices
- Clearing browser data will delete all workouts

## Usage Tips

1. **Starting Weights**: Be conservative! The program adds 5 lbs per workout
2. **Deload Protocol**: After 3 failures, reduce weight by 10% and rebuild
3. **Rest Times**: 3 minutes between sets (5 minutes for heavy squats/deadlifts)
4. **Frequency**: 3 times per week (e.g., Mon/Wed/Fri or Sun/Tue/Fri)
5. **Form First**: Always prioritize proper form over weight progression

## Customization

The app is built with vanilla React in a single HTML file. To customize:

1. Edit `index.html`
2. Modify workout templates (workoutA, workoutB arrays)
3. Adjust progression increment (default: +5 lbs)
4. Change deload percentage (default: -10%)
5. Customize exercises, rep schemes, etc.

## Browser Compatibility

- Chrome/Edge: Full support
- Firefox: Full support
- Safari: Full support
- Mobile browsers: Optimized for mobile

## License

Free to use and modify for personal use.

## Credits

Inspired by StrongLifts 5x5 by Mehdi Hadim
