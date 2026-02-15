# Button Image Customization Guide

## Overview
You can now customize each communication button with your own images from the resources folder!

## What's New

### 1. Resources Folder
- Location: `resources/images/`
- Purpose: Store your custom images for communication buttons
- Supported formats: JPG, PNG, GIF, WebP
- Recommended size: 400x400 pixels (square images work best)

### 2. Customize Button Images Section (in Settings)
Access via the ⚙️ settings icon, you'll find a new section called "🖼️ Customize Button Images"

**Features:**
- **Select Button to Customize**: Dropdown showing all available default buttons
- **Current Appearance**: Preview of how the button currently looks
- **Choose New Image**: File picker to select an image from your resources folder
- **Apply Image**: Save your custom image to the button
- **Reset to Default**: Restore the original emoji icon

### 3. How to Customize a Button

1. Open Settings (⚙️ icon)
2. Scroll to "🖼️ Customize Button Images"
3. Select a button from the dropdown (e.g., "Hungry (Needs)")
4. Click "📷 Choose Image from Resources"
5. Browse to `resources/images/` and select your image
6. Click "✓ Apply Image"
7. The button will immediately update!

### 4. How It Works

**Storage:**
- Button customizations are stored in browser localStorage
- Images are stored as base64 data URLs
- Customizations persist across sessions

**Button Rendering:**
- Each default button is identified by `category:index` (e.g., `needs:0` for "Hungry")
- If a custom image exists, it replaces the emoji
- If no custom image, the default emoji is used
- Custom buttons (created via "➕ Custom Buttons") work independently

### 5. Technical Details

**New JavaScript Variables:**
- `buttonImageCustomizations`: Object mapping button keys to image data URLs

**New Functions:**
- `populateButtonCustomizationDropdown()`: Fills the button selection dropdown
- `showButtonImageCustomizer()`: Shows preview and customization options
- `previewButtonCustomization()`: Previews selected image
- `applyButtonCustomization()`: Saves custom image to localStorage
- `resetButtonImage()`: Removes custom image and restores default

**Modified Functions:**
- `renderButtons()`: Now checks for custom images before rendering
- `loadSettings()`: Loads saved image customizations from localStorage
- `openSettings()`: Populates the customization dropdown

## Example Usage

### Scenario: Replace "Hungry" button emoji with a photo of food

1. Place `apple.jpg` in `resources/images/`
2. Open Settings
3. Select "Hungry (Needs)" from dropdown
4. Choose `apple.jpg`
5. Click "Apply Image"
6. The 🍎 emoji is now replaced with your apple photo!

### Scenario: Reset all buttons to emojis

For each button:
1. Select it from the dropdown
2. Click "🔄 Reset to Default"

## Benefits

✅ **Personalization**: Use photos of real objects, people, or places
✅ **Better Recognition**: Children may recognize photos better than emojis
✅ **Customizable**: Each button can have its own unique image
✅ **Reversible**: Easily reset to default emojis
✅ **Persistent**: Changes are saved and remembered

## Future Enhancements

Potential improvements:
- Batch import/export of customizations
- Pre-made image packs
- Image cropping tool
- Multiple image options per button
