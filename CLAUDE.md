# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Development
- `npm start` - Start Metro bundler
- `npm run ios` - Build and run iOS app (requires CocoaPods setup)
- `npm run android` - Build and run Android app

### iOS Dependencies
- `bundle install` - Install Ruby bundler (first-time setup)
- `bundle exec pod install` - Install CocoaPods dependencies (run after native dep updates)

### Code Quality
- `npm run lint` - Run ESLint
- `npm test` - Run Jest tests

### Build
- Direct build from Xcode (iOS) or Android Studio (Android)

## Project Architecture

### Technology Stack
- **Framework**: React Native 0.81.1
- **Language**: TypeScript with React 19.1.0
- **Testing**: Jest with React Test Renderer
- **Linting**: ESLint with @react-native/eslint-config
- **Bundler**: Metro
- **iOS**: CocoaPods for dependency management

### Project Structure
- `App.tsx` - Main application entry point with SafeAreaProvider wrapper
- `index.js` - React Native app registration
- `src/` - Source code directory
  - `PokedexApp.tsx` - Main app component with navigation setup
  - `assets/` - Application assets (images, icons)
  - `presentation/` - UI layer components
    - `navigator/` - Navigation configuration
      - `StackNavigator.tsx` - Stack navigation setup with route definitions
    - `screens/` - Screen components
      - `home/` - Home screen components
      - `pokemon/` - Pokemon detail screen components
      - `search/` - Search screen components
- `__tests__/` - Jest test files
- `android/` - Android-specific native code and configurations
- `ios/` - iOS-specific native code and configurations (Xcode project)

### Key Dependencies
- `@react-native/new-app-screen` - Default starter screen components
- `react-native-safe-area-context` - Safe area handling for modern devices
- `@react-navigation/native` - React Navigation core
- `@react-navigation/stack` - Stack navigator for screen transitions
- `react-native-screens` - Native screen management
- `react-native-gesture-handler` - Gesture handling for navigation
- `@react-native-masked-view/masked-view` - Masked view component for navigation animations

### Architecture Patterns
- Uses SafeAreaProvider for proper safe area handling across platforms
- Implements React Navigation stack navigator for screen management
- Follows presentation layer architecture with organized screen and navigator components
- Type-safe navigation with TypeScript route parameter definitions (RootStackParams)
- Follows standard React Native project structure from @react-native-community/cli
- TypeScript configuration extends @react-native/typescript-config
- Metro bundler with standard React Native configuration

### Navigation Structure
- **Stack Navigator**: Manages screen transitions and navigation state
- **Screens**:
  - `HomeScreen`: Main landing screen
  - `PokemonScreen`: Pokemon detail view (accepts pokemonId parameter)
  - `SearchScreen`: Pokemon search functionality
- **Route Types**: Strongly typed navigation parameters via RootStackParams interface

### Code Style
- Prettier configuration: single quotes, trailing commas, arrow parens avoided
- ESLint extends @react-native preset
- Format directive (`@format`) used in file headers