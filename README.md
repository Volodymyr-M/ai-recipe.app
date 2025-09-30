# Product Requirements Specification (PRS) for Love2Cook

**Version:** 2.0 **Last Updated:** 2025-09-18

## 1\. Vision & Core Value

**App Name:** Love2Cook **Platforms:** iOS & Android **Core Value Proposition:** Transform food photos into delicious, easy-to-follow recipes in seconds. Love2Cook is a smart culinary assistant that recognizes ingredients and dishes from your camera, providing personalized recipe suggestions tailored to your needs.

--------------------------------------------------------------------------------

## 2\. User Personas & Primary Use Cases

### 2.1\. Use Case 1: Restaurant Dish Discovery

- **Scenario:** A user is at a restaurant, enjoys their meal, and wants to find the recipe to cook it later.
- **Flow:**

  1. The user navigates to the "Detect" section of the app.
  2. They take a picture of the dish.
  3. The app's AI detects the food item and initiates a search for matching recipes.
  4. The user is presented with one or more recipe options.
  5. The scan is automatically saved to the user's history for future reference.

### 2.2\. Use Case 2: Specific Recipe Search at Home

- **Scenario:** A user is at home and knows what dish they want to cook.
- **Flow:**

  1. The user navigates to the "Food" section.
  2. They can either:

    - Search for the dish by typing its name.
    - Scan a sample of the food item with their camera.

  3. The app's AI detects the food (if scanned) and searches for matching recipes.

  4. The user is presented with one or more recipe options.

  5. If the camera was used, the scan is automatically saved to the user's history.

### 2.3\. Use Case 3: Ingredient-Based Recipe Generation

- **Scenario:** A user is at home and has several ingredients but is unsure what to make.
- **Flow:**

  1. The user navigates to the "Ingredients" section.
  2. They can either:

    - Take a picture of the ingredients.
    - Enter the ingredients manually via text.

  3. The app's AI detects the ingredients and searches for recipe options that use them.

  4. The user is presented with one or more recipe options.

  5. If the camera was used, the scan is automatically saved to the user's history.

### 2.4\. Use Case 4: Browsing Saved Recipes

- **Scenario:** A user wants to find a previously generated or favorited recipe to cook or review.
- **Flow:**

  1. The user navigates to the "Recipes" section.
  2. They are presented with a list of all recently generated recipes.
  3. The user can apply a filter to view only the recipes they have marked as "Favorite."

--------------------------------------------------------------------------------

## 3\. Functional Requirements

### 3.1\. Onboarding

- **FR1.1: Onboarding Flow:** Upon first launch, new users must be guided through a sequential onboarding flow consisting of the following steps in order:

  1. **Welcome Screens:** A series of screens that reiterate the app's marketing benefits and core features.
  2. **Food Preferences:** A page for the user to set their initial food preferences.
  3. **Paywall:** A skippable paywall screen presenting the subscription options.

- **FR1.2: Onboarding Completion:** The app must track whether the user has completed the onboarding flow to prevent it from showing on subsequent launches.

### 3.2\. Food Preferences & Personalization

- **FR2.1: Preference Management:** Users must be able to set and update their food preferences. These settings must be accessible from the Settings screen after the initial onboarding.
- **FR2.2: Preference Levels:** For each food item or category, the user can select one of three options:

  - **Like:** The user enjoys this food.
  - **Neutral:** The user has no preference (this is the default setting).
  - **Avoid:** The user wants to avoid recipes containing this food.

- **FR2.3: Preference Categories & Items:** The preferences must be organized into the following structure, allowing users to set a preference for an entire category or a specific item:

  - **Meat:**

    - Pork
    - Beef
    - Poultry

  - **Fish & Seafood:**

    - Fish
    - Shellfish

  - **Dairy & Eggs:**

    - Milk
    - Eggs

  - **Gluten**

  - **Other:**

    - Peanuts
    - Nuts
    - Soy

### 3.3\. Food Recognition (Scanning)

- **FR3.1: Image Capture:** Users must be able to capture an image of food items using the device's camera.
- **FR3.2: Image Import:** Users must be able to import an existing image from the device's photo gallery.
- **FR3.3: Scan Processing:** After image submission, the app must initiate a processing state to analyze the image using AI.
- **FR3.4: Recognition Results:** The app must identify one or more food items from the image and present these results to the user.

### 3.4\. Search & Suggestions

- **FR4.1: Contextual Suggestions:** When a user enters text into a search field (for either food dishes or ingredients), the app must provide intelligent suggestions to facilitate easier entry.
- **FR4.2: Two-Stage Suggestion System:** The suggestion mechanism must operate in two stages:

  1. **Initial Suggestions:** Immediately upon text entry, display a list of relevant suggestions from a predefined, local list of popular foods or ingredients (depending on the search context).
  2. **AI-Powered Suggestions:** In parallel, send a background request to the AI to generate smarter, more contextually relevant suggestions. Once loaded, these AI-powered suggestions should be displayed to the user.

### 3.5\. Recipe Generation & Details

- **FR5.1: Recipe Generation:** Based on a successful scan or search, the app (through AI) must generate one or more relevant recipes.
- **FR5.2: Recipe Title & Description:** Each recipe must have a clear, descriptive title and a brief summary.
- **FR5.3: Time & Servings:** Each recipe must contain:

  - Preparation time.
  - Cooking time.
  - Number of servings.

- **FR5.4: Difficulty Level:** Each recipe must be assigned a difficulty level (e.g., `Easy`, `Medium`, `Hard`).

- **FR5.5: Ingredients List:** Each recipe must include a detailed list of ingredients, specifying:

  - Ingredient name.
  - Quantity required.
  - Measurement unit (e.g., grams, cups, pieces).
  - An optional flag for non-essential ingredients.

- **FR5.6: Step-by-Step Instructions:** Each recipe must provide a sequence of cooking instructions, where each step includes:

  - A step number.
  - A clear description of the action to be performed.
  - An optional timer to help the user cook the dish.

- **FR5.7: Nutritional Information:** Each recipe must provide estimated nutritional information per serving, including:

  - Calories
  - Protein (g)
  - Carbohydrates (g)
  - Fat (g)
  - Fiber (g)
  - Sugar (g)
  - Sodium (mg)

- **FR5.8: AI-Generated Imagery:** For users with an active subscription, the app must generate a unique illustration for each recipe. This image represents the final dish.

### 3.6\. Recipe Card Display & Interaction

- **FR6.1: Recipe Card Content:** When displayed in a list (e.g., search results, recent recipes), each recipe card must show the recipe's Name, Description, Cooking Time, and total Calories. If an AI-generated illustration is available, it must also be displayed on the card.
- **FR6.2: Lazy Loading (Enrichment):** The app must only load the basic card content initially. Full recipe details (like the complete ingredient list, step-by-step instructions, and the AI-generated illustration) must be fetched on-demand in a process called "enrichment."
- **FR6.3: Enrichment Triggers:** Enrichment must be triggered when the user either:

  - Taps on a recipe card to view its full details.
  - Adds the recipe to their Favorites list.

- **FR6.4: Card Actions:** Each recipe card must provide the following actions:

  - **Share:** Allow the user to share the recipe as text using the native OS sharing functionality.
  - **Delete:** Allow the user to delete the recipe from the database. This action must trigger a confirmation dialog before proceeding and must also remove any AI-generated images stored for that recipe.
  - **Add to Favorites:** Allow the user to add or remove the recipe from their Favorites list.

### 3.7\. Recipe Details Screen

- **FR7.1: Navigation:** Users must be able to navigate to the Recipe Details screen by tapping on any recipe card from any list (e.g., search results, recent recipes, favorites).
- **FR7.2: Enriched Content Display:** Upon opening, the screen must display all available recipe information, including:

  - The AI-generated illustration (if available).
  - Name and Description.
  - Preparation Time and Cooking Time.
  - Difficulty Level (e.g., Easy, Medium, Hard).
  - Calories.
  - A complete list of ingredients with quantities.
  - Step-by-step cooking instructions.
  - Detailed nutritional information (Protein, Carbohydrates, Fat, Fiber, Sugar, Sodium).

- **FR7.3: Available Actions:** The screen must provide the user with the following actions:

  - **Enter Cooking Mode:** A button to launch the step-by-step Cooking Mode interface.
  - **Add to Favorites:** A toggle to add or remove the recipe from the user's Favorites list.
  - **Share:** Allow the user to share the recipe's text content via the native OS sharing functionality.
  - **Export:** Present the user with multiple options to export the recipe data.

- **FR7.4: Export Options:** The "Export" action must provide the following formats:

  - Plain Text (.txt)
  - JSON Data (.json)
  - Spreadsheet (.csv)
  - Markdown (.md)
  - PDF (.pdf)

### 3.8\. Ingredients Mode

- **FR8.1: Ingredient Input:** Users must be able to provide a list of ingredients either by scanning them or by manual text entry.
- **FR8.2: Recipe Generation from Ingredients:** Based on the provided ingredients, the app must generate one or more relevant recipes.
- **FR8.3: Quick Add List:** To facilitate entering ingredients, a "Quick Add" list of common ingredients must be shown below the search field.
- **FR8.4: Quick Add Interaction:** When a user taps an item from the list, its name must be added to the search field without initiating the search.
- **FR8.5: Quick Add Content:** The list must contain 30 predefined, localizable items stored within the app (not in the database). Each item must have a name and an illustrative image. The list must represent the top 30 most common ingredients in US households, ordered by popularity.
- **FR8.6: Quick Add Filtering and Linking:** The list of items shown to the user must be filtered to exclude ingredients corresponding to Food Preferences the user has marked to "Avoid." After filtering, a maximum of the top 20 items must be displayed. Each Quick Add item must be linked to its relevant Food Preference category where applicable (e.g., "chicken breasts" linked to "Poultry").
- **FR8.7: Quick Add Alphabetical Sorting:** The Quick Add ingredient list must be displayed in alphabetical order by ingredient name (case-insensitive) to enable users to easily locate specific ingredients. This sorting must be applied both to the full list and to the filtered list after food preference filtering.

### 3.9\. Recipe Interaction

- **FR9.1: Favorite Recipes:** Users must be able to mark any recipe as a "favorite."

### 3.10\. Cooking Mode

- **FR10.1: Step-by-Step View:** From a recipe's detail screen, users must be able to enter a dedicated "Cooking Mode."
- **FR10.2: Guided Instructions:** This mode must present the cooking instructions one step at a time in a clear, focused interface.
- **FR10.3: Integrated Timers:** For any instruction step that includes a duration (as defined by the AI-generated recipe), the Cooking Mode must provide an integrated timer.
- **FR10.4: Timer Functionality:** The timer must:

  - Be started manually by the user.
  - Display a visible countdown on the screen while active.
  - Trigger a push notification upon completion to alert the user.

- **FR10.5: Timer Notifications Control:** The push notification for the timer must be controllable via the dedicated toggle in the app's "Notification Preferences" settings.

- **FR10.6: Screen Wake Lock:** While the user is in Cooking Mode, the app must prevent the screen from turning off by the OS to ensure continuous visibility of cooking instructions and timers.

### 3.11\. Recipe Collection

- **FR11.1: Automatic Recipe Saving:** All recipes generated from a search (regardless of the use case) must be automatically saved to the local database.
- **FR11.2: Recipes Section:** The app must feature a dedicated "Recipes" section.
- **FR11.3: Recent Recipes:** Within the "Recipes" section, users must be able to view a list of recently generated or viewed recipes.
- **FR11.4: Favorite Recipes View:** The "Recipes" section must also provide a view to access all recipes that the user has marked as a favorite.
- **FR11.5: Search Recipes:** Users must be able to search for recipes by name or ingredients within the "Recipes" section.
- **FR11.6: Clear All Recipes:** The app must provide an option for the user to delete all recipes from their collection. This action must require user confirmation before proceeding. When clearing all recipes, the app must also delete all associated recipe images from the file system to free up storage space.
- **FR11.7: Export Collection:** The app must allow users to export their entire recipe collection in the following formats:

  - Plain Text (.txt)
  - JSON Data (.json)
  - Spreadsheet (.csv)
  - Markdown (.md)

### 3.12\. Scan History

- **FR12.1: Automatic Saving:** All scans initiated via the device's camera must be automatically saved to a user-accessible scan history section.
- **FR12.2: Scan History Item Details:** Each item in the scan history must display:

  - A thumbnail of the scanned image.
  - The names of recognized items (e.g., foods, ingredients, or a shortened version of recognized text).

- **FR12.3: Scan Actions:** Users must be able to perform the following actions on individual scans in the scan history:

  - **View Details:** Navigate to a dedicated Scan Details screen.
  - **Add to Favorites:** Add or remove the scan from a favorites list.
  - **Share:** Share the scan details via the native OS sharing functionality.
  - **Delete:** Permanently delete a scan from the history, requiring user confirmation, and remove any stored scan images (original and thumbnail) tied to that scan.

- **FR12.4: Scan Details Screen:** The Scan Details screen must allow the user to navigate to the list of recipes that were generated from that specific scan.

- **FR12.5: Delete All Scans:** The app must provide an option for the user to permanently delete all scans from their history, requiring user confirmation before proceeding. When clearing all scans, the app must also delete all stored scan images (originals and thumbnails).

### 3.13\. User Settings

- **FR13.1: Measurement System:** Users must be able to choose between `Metric` and `Imperial` measurement systems. The selected unit must be reflected in all recipe ingredient quantities.
  - **FR13.1a: Automatic Measurement Detection:** On first launch, the app must detect the appropriate measurement system based on the device's country code. Imperial system is used for US, Liberia, and Myanmar; Metric system is used for all other countries.
- **FR13.2: Theme Selection:** The application must support both a light and a dark theme. In Settings, the user must be able to switch between `Light`, `Dark`, and `System` themes. The `System` option, which adapts to the OS-defined appearance, must be the default setting.
- **FR13.3: Font Size:** Users must be able to select from a range of font sizes (e.g., `Small`, `Medium`, `Large`, `Extra Large`) from the Settings screen to improve readability.
- **FR13.4: Supported Languages:** The application must support the following languages: English (default), German, Spanish, Italian, French, Portuguese (Brazil), and Ukrainian.
- **FR13.5: Automatic Language Detection:** On first launch, the app must detect the device's OS language using only the language code (e.g., "pt" from "pt_BR") to support all language variants. Portuguese users from both Brazil and Portugal will see Portuguese language. If the detected language is supported, it will be used as the display language. If the language is not supported, the app will default to English.
- **FR13.6: Manual Language Selection:** Users must be able to manually select their preferred language from the list of supported languages in the Settings screen, overriding any automatically detected setting.
- **FR13.7: Notification Preferences:** Users must be able to enable or disable all application notifications via a single master toggle switch in the Settings screen.
- **FR13.8: Clear All Data:** Users must be able to reset the application to its initial state via a "Clear All Data" option in Settings. This action must:

  - Reset all user settings to their defaults, including language preferences. This will force the app to immediately re-detect the system language, as it does on the first start.
  - Delete all entries from the local database (including scans, recipes, and favorites).
  - Remove all app-generated files from the device's storage (e.g., recipe images).
  - Ensure the onboarding flow is displayed on the next app launch.

- **FR13.9: Contact Support:** Users must be able to contact support by tapping a "Contact Us" item in Settings, which must open the default email client.

### 3.14\. Monetization & Paywall

- **FR14.1: Subscription Plans:** The app must offer two auto-renewing subscription plans:

  - A **Weekly Plan**.
  - A **Yearly Plan**.

- **FR14.2: Free Trial:** The **Weekly Plan** must include a one-time, 3-day free trial for new users. The Yearly Plan does not offer a free trial.

- **FR14.3: Trial Reminder Notification:** A local notification must be scheduled to be sent to the user 1 day before their free trial is set to expire, reminding them of the upcoming charge. This is a transactional notification and must be sent regardless of the user's general notification preferences in Settings.

- **FR14.4: Paywall Presentation:** A paywall screen presenting these subscription options must be displayed during the onboarding flow and must be accessible from the Settings screen. The paywall presented during onboarding must feature a clear and easily accessible option for the user to skip the purchase.
- **FR14.5: Premium Feature Access:** Access to premium features (specifically, AI-generated recipe illustrations) is granted to any user with an active subscription or an active free trial.
- **FR14.6: Restore Purchases:** The app must provide a mechanism for users to restore their previous purchases, allowing them to regain premium access on any of their devices.

### 3.15\. User Feedback

- **FR15.1: "Rate Us" Popup:** The app must include a standard "Rate Us" popup from the app store to solicit user feedback.
- **FR15.2: Manual Trigger:** Users must be able to manually trigger the "Rate Us" popup from the Settings screen.
- **FR15.3: Automatic Trigger:** The popup must be shown automatically once after a number of conditions is met: the user opens their generated recipe details, the recipe is enriched with all non-image details, and a small delay has passed. If these conditions are met, the popup must be shown even if the user navigates away from the recipe details screen.
- **FR15.4: Recurring Cooldown Period:** The automatic popup must be shown again after the above mentioned conditions are met, but not before at least two weeks has passed since it was last shown automatically.

### 3.16\. Quick Ideas

- **FR16.1: Default View:** By default, the app must display a list of "Quick Ideas" for dishes to cook.
- **FR16.2: Predefined Content:** The app must include a predefined, local collection of 90 quick ideas, categorized by mealtime:

  - 30 ideas for Breakfast.
  - 30 ideas for Lunch.
  - 30 ideas for Dinner.

- **FR16.3: Content Mix:** For each mealtime, the list of 30 ideas must consist of:

  - 20 popular dishes common in the US.
  - 10 exotic or less common dishes.

- **FR16.4: Time-of-Day Filtering:** The list of ideas shown to the user must be automatically filtered based on the current time of day (e.g., breakfast ideas in the morning, lunch ideas around noon, dinner ideas in the evening).

- **FR16.5: Display Limit:** A maximum of the top 18 relevant quick ideas must be displayed to the user at any given time.

- **FR16.6: Category Organization:** All quick ideas must be organized into four main categories for improved user experience:

  - **Quick & Easy:** Items with preparation time ≤ 15 minutes, perfect for users seeking fast meal solutions.
  - **Comfort Food:** Classic American favorites and traditional dishes that users commonly recognize and enjoy.
  - **International:** Exotic or less common dishes from various cuisines around the world (items marked as `isExotic: true`).
  - **Healthy Options:** Dishes containing fish, salads, grilled items, and other health-conscious meal choices.

- **FR16.7: Categorized Display:** Quick ideas must be presented in organized sections by category, with each section displaying:

  - A category header with icon and name (e.g., ⚡ "Quick & Easy", 🌍 "International").
  - A responsive grid of idea cards relevant to that category.
  - Empty state handling when no ideas are available for a category.

- **FR16.8: Food Preference Integration:**

  - Each quick idea must be internally mapped to the specific food preference items it contains (e.g., a Caesar Salad idea is linked to "Poultry" and "Eggs").
  - The displayed list must be dynamically sorted based on the user's Food Preferences: ideas containing "Liked" ingredients appear at the top, and those with "Avoided" ingredients appear at the bottom.
  - Category filtering must respect user preferences, ensuring only appropriate ideas are shown in each section.

- **FR16.9: Card Display:** Each quick idea must be presented on a card that includes:

  - An image of the dish.
  - The name of the dish (e.g., "Vegan Burger").
  - The total preparation and cooking time.
  - The cooking difficulty level (`Easy`, `Medium`, or `Hard`).
  - A badge indicating if the dish is considered "exotic".

- **FR16.10: Local Storage & Localization:** The entire collection of 90 quick ideas must be stored locally as part of the app's assets (not in the database) and must be fully localizable.

- **FR16.11: Tap Action:** When a user taps on a Quick Idea card, the app must initiate an AI search request for recipes using the name of the dish from the card. This action should be equivalent to the user manually typing the dish name into the search field.

### 3.17\. Smart Recipe Detect

- **FR17.1: Smart Detect Button:** The app must feature a universal "Detect Recipe" button as a single entry point for all camera-based recognition tasks.
- **FR17.2: Context-Aware Recognition:** This feature must intelligently detect the content of the captured image and initiate the appropriate user flow. Supported contexts include a finished dish, a group of ingredients, or text.
- **FR17.3: Standard Flow Integration:**

  - If a **finished dish** is detected, the app must trigger the standard recipe search flow.
  - If a group of **ingredients** is detected, the app must trigger the ingredient-based recipe generation flow.

- **FR17.4: Text Recognition and Processing:** If text is detected, the app must perform Optical Character Recognition (OCR) and analyze the content:

  - **Food Names:** If the text contains names of dishes (e.g., from a menu), the app must initiate a recipe search for those dishes.
  - **Ingredient Names:** If the text is a list of ingredients, it must trigger the ingredient-based recipe generation flow.
  - **Full Recipe Text:**: If the text is a full recipe, the AI must parse it and convert it into the app's standard recipe format, presenting it as a search result.

### 3.18\. Inspirations

- **FR18.1: Default Inspirations View:** By default, the app must display a list of "Inspirations."
- **FR18.2: Inspiration Definition:** An Inspiration is a complete, predefined recipe stored locally within the app, not the database. Each Inspiration is fully enriched, including a recipe image, and is fully localizable.
- **FR18.3: Tap Action:** When a user taps on an Inspiration, the app must navigate directly to the Recipe Details screen for that recipe.
- **FR18.4: Predefined Content:** The app must include a local collection of 30 predefined Inspirations, categorized by mealtime:

  - 10 for Breakfast
  - 10 for Lunch
  - 10 for Dinner

- **FR18.5: Filtering and Display:**

  - The list of Inspirations must be automatically filtered based on the current time of day (e.g., breakfast in the morning).
  - From the time-filtered list, a set of 5 Inspirations must be randomly selected and displayed to the user.

- **FR18.6: Content Constraints:** The set of predefined Inspirations must consist of healthy food and drink options that do not contain any ingredients that can be restricted via Food Preferences (e.g., no meat, fish, gluten, dairy, eggs, nuts, or soy).

### 3.19\. Debug Console

- **FR19.1: Development-Only Access:** The app must provide a debug console accessible only in debug builds through the Development section of Settings.
- **FR19.2: Log Display:** The debug console must display all application logs (debug, info, warning, error) that existed before the dialog was opened, not just real-time streaming errors.
- **FR19.3: Historical Log Access:** Users must be able to view log entries that were created before opening the debug console dialog.
- **FR19.4: Memory Management:** Log storage must be limited to a maximum of 200 entries in debug mode to prevent memory issues.
- **FR19.5: Production Safety:** Log storage must have zero memory overhead in production/release builds - no log entries should be stored when `kDebugMode` is false.
- **FR19.6: Log Export:** The debug console must provide functionality to export all logs as a text file for sharing with developers.
- **FR19.7: Clipboard Copy:** The debug console must provide a "Copy All" button to copy all displayed logs to the device clipboard for easy sharing.
- **FR19.8: Text Selection:** Individual log entries must be selectable, allowing users to copy specific log lines or ranges of text to the clipboard.
- **FR19.9: Log Clearing:** Users must be able to clear all stored log entries from the debug console.
- **FR19.10: Color-Coded Display:** The debug console must display logs with color coding and icons for different log levels (debug: grey, info: blue, warning: orange, error: red, fatal: purple) to improve visual identification.
- **FR19.11: Log Level Filtering:** Users must be able to filter displayed logs by log level using toggle-able filter chips, allowing them to show/hide specific types of logs (debug, info, warning, error, fatal).
- **FR19.12: Filtered Copy:** The debug console must provide separate "Copy Filtered" and "Copy All" buttons - "Copy Filtered" copies only currently visible logs based on active filters, while "Copy All" copies all stored logs regardless of filters.
- **FR19.13: Individual Log Copy:** Each log entry must display a small copy icon button that allows users to copy that specific log entry to the clipboard with a single tap.
- **FR19.14: Individual Log Share:** Each log entry must display a small share icon button that allows users to share that specific log entry with other apps via the system share dialog.
- **FR19.15: Bulk Log Sharing:** The debug console must provide "Share Filtered" and "Share All" buttons that allow users to share multiple log entries via the system share dialog - "Share Filtered" shares only currently visible logs based on active filters, while "Share All" shares all stored logs regardless of filters.

--------------------------------------------------------------------------------

## 4\. Non-Functional Requirements

### 4.1\. User Interface & User Experience (UI/UX)

- **NFR1.1: Screen Orientation:**
  - **iPhone and Android devices:** The application must be locked to portrait orientation and must not rotate into landscape mode.
  - **iPad devices:** The application must support all interface orientations (portrait, portrait upside-down, landscape left, and landscape right) to meet Apple's multitasking requirements.

### 4.2\. AI Model Specifications

- **NFR2.1: Recipe Generation & Suggestions:** All AI-driven recipe generation and suggestion features must use models provided by OpenAI.
- **NFR2.2: Image Generation:** AI-generated recipe illustrations must be created using the `models/gemini-2.5-flash-image-preview` model.

### 4.3\. Performance

- **NFR3.1: Responsiveness:** The UI must remain responsive and interactive at all times, especially during background tasks like image processing or data fetching.
- **NFR3.2: Lazy Loading:** Detailed recipe information (e.g., full instructions, AI-generated images) should be loaded on-demand to minimize initial load times.

### 4.4\. Data Management & Persistence

- **NFR4.1: Local Storage:** All user-generated data (scans, favorites, settings) must be persisted locally on the device.
- **NFR4.2: Data Integrity:** The application must handle data serialization and deserialization robustly, with fallbacks for malformed data to prevent crashes.
- **NFR4.3: Data Validation:** Input and retrieved data must be validated to ensure it falls within expected parameters (e.g., non-negative nutritional values).
- **NFR4.4: Timestamps:** All key user actions (creating a scan, generating a recipe, viewing a recipe) must be timestamped (`createdAt`, `updatedAt`, `lastViewedAt`).
- **NFR4.5: Initial Version Tracking:** On the very first launch of the application, its version number must be saved to persistent local storage. This value must not be overwritten on subsequent app updates, allowing for future "grandfathering" of users.

### 4.5\. Error Handling

- **NFR5.1: Clear Error Messages:** In case of a failure (e.g., scan recognition fails, network error), the app must display a clear, user-friendly error message and suggest a course of action (e.g., "Try again").
- **NFR5.2: Graceful Degradation:** The app should handle unexpected data states gracefully (e.g., a recipe with missing instructions should not crash the app).

--------------------------------------------------------------------------------

## 5\. Future Features

- **Gamification:** Achievements, badges, and streaks for user engagement.
- **Recipe Notes:** The ability for users to add and save personal text notes to a recipe.
- **Manual Recipe Management:** The ability for users to manually enter a new recipe or edit an existing one.
- **PDF Export:** The ability to export the entire recipe collection as a formatted PDF document.
- **Cooking Mode Voice Control:** The ability to navigate cooking steps using voice commands like "Next step" or "Repeat step."
- **Smart Substitutions:** An AI-powered feature that suggests locally available alternatives for ingredients the user does not have (e.g., "no sour cream? use yogurt").
- **Daily Recipe Push:** A daily notification that suggests a new recipe based on the user's scan history (e.g., "Today's recipe based on yesterday's scan").
- **Tags & Categories:** Recipes can be associated with tags (e.g., `Vegan`, `QuickMeal`, `Italian`) for filtering and discovery.
- **Meal Planning & Shopping Lists:** Plan multi-day meal schedules and generate shopping lists covering only the ingredients a user is missing.

--------------------------------------------------------------------------------

## 6\. Analytics & Tracking

To gain insights into user behavior and app performance, the following analytics events must be tracked.

### 6.1\. Onboarding Events

These events will help understand how users are progressing through the initial setup and where they might be dropping off.

Event Name                  | Description                                   | Parameters
:-------------------------- | :-------------------------------------------- | :-----------------------------------------------------------
`onboarding_started`        | User begins the onboarding flow.              | -
`onboarding_step_completed` | User completes a specific step in onboarding. | `step_name` (e.g., 'welcome', 'food_preferences', 'paywall')
`onboarding_skipped`        | User skips the onboarding paywall.            | `step_name` ('paywall')
`onboarding_completed`      | User finishes the entire onboarding process.  | -

### 6.2\. Core Feature Events

Tracking these events is crucial for understanding how core features--like scanning, searching, and recipe generation--are being used.

Event Name         | Description                                        | Parameters
:----------------- | :------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------
`scan_initiated`   | User starts a food scan.                           | `source` ('camera', 'gallery'), `use_case` ('restaurant_dish', 'home_recipe', 'ingredients')
`scan_completed`   | A scan successfully recognizes items.              | `scan_id`, `recognized_items` (array), `item_count`, `generated_recipe_titles` (array, optional), `generated_recipe_count` (optional)
`scan_failed`      | A scan fails to produce results.                   | `scan_id`, `error_reason`
`manual_search`    | User searches for a recipe or ingredient via text. | `search_context` ('food', 'ingredients'), `query`
`recipe_generated` | One or more recipes are generated.                 | `source` ('scan', 'search'), `recipe_count`

**Note on `scan_completed` Event**: This event now tracks both the actual food items recognized from the image scan (`recognized_items`) and the titles of the recipes generated from those items (`generated_recipe_titles`). This dual tracking allows for better analysis of scan accuracy and recipe generation success.

### 6.3\. User Engagement Events

These events measure how users interact with the recipes and other content, giving a sense of what they find valuable.

Event Name             | Description                                  | Parameters
:--------------------- | :------------------------------------------- | :-----------------------------------------
`recipe_viewed`        | User opens the details screen for a recipe.  | `recipe_id`, `recipe_name`, `source`
`recipe_favorited`     | User adds a recipe to their favorites.       | `recipe_id`, `recipe_name`
`recipe_shared`        | User shares a recipe.                        | `recipe_id`, `recipe_name`, `share_method`
`recipe_exported`      | User exports a single recipe.                | `recipe_id`, `export_format`
`collection_exported`  | User exports their entire recipe collection. | `export_format`
`cooking_mode_started` | User enters the step-by-step cooking mode.   | `recipe_id`, `recipe_name`
`rate_us_popup_shown`  | The "Rate Us" prompt is displayed.           | `trigger` ('automatic', 'manual')

### 6.4\. Monetization Events

It's vital to track how users interact with your paywall and subscription options to optimize your revenue.

Event Name                | Description                         | Parameters
:------------------------ | :---------------------------------- | :-----------------------------------------------------
`paywall_viewed`          | User is shown the paywall.          | `source` ('onboarding', 'settings')
`subscription_initiated`  | User taps on a subscription option. | `plan` ('weekly', 'yearly'), `has_trial` (true/false)
`subscription_successful` | User successfully subscribes.       | `plan`, `has_trial`
`subscription_failed`     | A subscription purchase fails.      | `plan`, `error_reason`
`trial_started`           | User begins a free trial.           | `plan` ('weekly')
`purchase_restored`       | User restores a previous purchase.  | -

### 6.5\. Settings & Preference Events

These events will show you how users are personalizing their app experience.

Event Name                 | Description                                           | Parameters
:------------------------- | :---------------------------------------------------- | :----------------------------------------------------------------------------
`settings_changed`         | User changes a setting.                               | `setting_name` (e.g., 'theme', 'language', 'measurement_system'), `new_value`
`food_preferences_updated` | User updates their food preferences after onboarding. | `change_type` ('like', 'avoid', 'neutral'), `item_or_category`
`all_data_cleared`         | User uses the "Clear All Data" option.                | -
