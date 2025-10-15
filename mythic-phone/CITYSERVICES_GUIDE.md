# City Services App - Adding New Businesses

## Quick Guide

The City Services app automatically displays all on-duty businesses. To add a new business type with custom icons and categories, follow these steps:

## 1. Update BusinessCard.jsx

**File:** `mythic-phone/ui/src/Apps/cityservices/components/BusinessCard.jsx`

### Add Icon Detection

Find the `getBusinessIcon()` function and add your business pattern:

```javascript
// Your Business Type
if (jobIdLower.includes('yourbusiness') || jobIdLower.includes('keyword')) {
    return 'icon-name';  // FontAwesome icon name
}
```

### Add Category Label

Find the `getBusinessType()` function and add your business pattern:

```javascript
// Your Business Type
if (jobIdLower.includes('yourbusiness') || jobIdLower.includes('keyword')) {
    return 'Your Category';
}
```

## 2. Available FontAwesome Icons

Common icons you can use:
- `wrench` - Mechanics
- `utensils` - Restaurants
- `martini-glass` - Bars
- `shop` - Stores
- `car-building` - Dealerships
- `taxi` - Taxi services
- `warehouse` - Storage
- `building` - Real Estate
- `shield` - Security/Police
- `briefcase` - Generic business

## 3. Rebuild UI

After making changes:

```bash
cd mythic-phone/ui
npm run build
```

Then restart the resource:
```
restart mythic-phone
```

## 4. Exclude Jobs (Optional)

If you want to exclude certain jobs from showing in City Services:

**File:** `mythic-phone/server/apps/cityservices.lua`

Update the `isExcluded` line:

```lua
local isExcluded = onDuty == "ems" or onDuty == "government" or onDuty == "prison" or onDuty == "yourjob"
```

## Example: Adding a Tow Company

```javascript
// In getBusinessIcon()
if (jobIdLower.includes('tow') || jobIdLower.includes('impound')) {
    return 'truck-tow';
}

// In getBusinessType()
if (jobIdLower.includes('tow') || jobIdLower.includes('impound')) {
    return 'Towing';
}
```

## Notes

- The app automatically detects on-duty players using `Player(src).state.onDuty`
- Job IDs are checked case-insensitively
- Multiple keywords can be used for the same business type
- Police has special workplace tracking (LSPD, BCSO, SASP)
