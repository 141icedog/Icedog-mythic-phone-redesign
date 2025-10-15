# 📱 Mythic Phone - Redesigned - Icedog

A complete overhaul of the Mythic Framework phone system with a modern interface, new applications, and enhanced features for FiveM roleplay servers.

## 🎨 What's New

### **Visual Redesign**
- Modern, clean UI with improved color schemes
- Smoother animations and transitions
- Enhanced readability and contrast
- Responsive design optimizations
- Updated icons throughout

### **New Apps**

#### 🏢 City Services
A real-time business directory that revolutionizes how players find services:
- **Live Business Tracking** - See all active businesses with on-duty employees
- **Smart Search** - Quickly find the services you need
- **Police Department Breakdown** - Special tracking for LSPD, BCSO, and SASP
- **50+ Business Icons** - Unique icons for mechanics, restaurants, bars, shops, and more
- **Last Updated Timestamp** - Know when data was refreshed
- **Zero Configuration** - Automatically pulls from mythic-jobs

### **Enhanced Features**
- Improved performance and load times
- Better error handling and user feedback
- Optimized NUI callbacks
- Cleaner codebase with better documentation
- Mobile-first responsive design

## ✨ Key Features

### **City Services App**
- **Real-Time Updates** - Refresh to see current business activity
- **Employee Counts** - Know how many staff are working
- **Department Tracking** - Police shows Officers, Deputies, and Troopers separately
- **Pattern Matching** - Automatically categorizes businesses with appropriate icons
- **Search Functionality** - Filter businesses instantly
- **Empty State Handling** - Clear messaging when no businesses are active

### **UI/UX Improvements**
- Consistent design language across all apps
- Improved touch targets for better usability
- Loading states and spinners
- Toast notifications for actions
- Smooth page transitions

## 📸 Preview

### City Services App
![City Services](images(ignore)/city-services.png)

### Police Department Breakdown
![Police Departments](images(ignore)/police-breakdown.png)

### Notification Functionality (credit to @tyh, Ui by Me)
![Notification](images(ignore)/notification.png)



## 🚀 Installation

### **Requirements**
- Mythic Framework (Base + Jobs)
- FiveM Server (Latest artifacts recommended)
- Node.js v14+ (for building UI)

### **Steps**

1. **Backup your current phone** (important!)
   ```bash
   # Make a copy of your existing mythic-phone folder
   ```

2. **Replace the resource**
   - Delete or rename your old `mythic-phone` folder
   - Extract this version to `resources/[mythic]/mythic-phone`

3. **Install dependencies and build**
   ```bash
   cd resources/[mythic]/mythic-phone/ui
   npm install
   npm run build
   ```

4. **Restart your server**
   ```
   restart mythic-phone
   ```

That's it! The City Services app will automatically detect jobs from mythic-jobs.

---

## 🎯 What Changed?

### **City Services (NEW)**
- Brand new app for finding active businesses
- Automatic job detection from mythic-jobs
- Special police workplace tracking
- Comprehensive business categorization

### **UI Redesign**
- Modernized color palette
- Improved spacing and typography
- Better contrast ratios
- Smoother animations
- Optimized for readability

### **Performance**
- Reduced bundle size
- Faster load times
- Optimized re-renders
- Better state management
- Cleaner NUI callbacks

## 🎨 Supported Business Types

The City Services app automatically recognizes and displays:

**Services:** Mechanics • Towing • Dealerships  
**Food & Drink:** Restaurants • Bars • Cafes • Bakeries  
**Retail:** Shops • Stores • Pawn Shops  
**Professional:** Real Estate • Security • Taxi  
**Entertainment:** Bowling • Casinos • Arcades  
**Other:** Storage • Dispensaries • Organizations

## 🔧 Configuration

### **Adding Custom Business Types**

See mythic-phone > CITYSERVICES_GUIDE.md for detailed instructions on:
- Adding new business icons
- Creating custom categories
- Excluding specific jobs
- Customizing colors and styles

### **Excluding Jobs from City Services**

Edit `server/apps/cityservices.lua`:
```lua
local isExcluded = onDuty == "ems" or onDuty == "government" or onDuty == "yourjob"
```

---

## 🐛 Troubleshooting

### **City Services shows no businesses**
- Ensure players are on duty: `Player(src).state.onDuty` must be set
- Verify jobs exist in mythic-jobs
- Check server console for errors

### **Wrong employee count**
- Verify on duty state is set correctly
- Check if job is excluded in server code

### **Police workplaces not showing**
- Verify `Player(src).state.onDutyWorkplace` is set
- Check workplace ID matches (lspd/lscso/sasp)

### **UI not building**
- Ensure Node.js v14+ is installed
- Delete `node_modules` and run `npm install` again
- Check for errors in build output

---

## 📝 Changelog

### v1.0.0 - Complete Redesign
- **NEW:** City Services app with real-time business tracking
- **NEW:** Police department workplace breakdown (LSPD/BCSO/SASP)
- **NEW:** Last updated timestamp with time ago display
- **IMPROVED:** Modern UI design across all apps
- **IMPROVED:** Performance optimizations and faster load times
- **IMPROVED:** Better error handling and user feedback
- **IMPROVED:** Enhanced documentation with technical guides
- **FIXED:** Various UI bugs and inconsistencies

---

## 💬 Support

- **Offical Mythic Discord** [Mythic Framework Offical](https://discord.gg/JGNfR4sZwv)


## 🙏 Credits

- **Original Mythic Phone:** Mythic Framework Team
- **Notificaiton System** Tyh
- **Redesign & City Services:** IceDog
- **Icons:** FontAwesome
- **Framework:** React, Material-UI

---

## ⭐ Show Your Support

If you like this redesign, please star the repository and share it with others!

---

**Made with ❤️ for the mythic-framework community**
