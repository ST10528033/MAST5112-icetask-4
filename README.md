MAST5112-icetask-4

Weather Dashboard Application

 1. Introduction
The Weather Dashboard application is a React Native mobile application built with Expo[cite: 1, 7]. It displays detailed weather information for three selected cities (Johannesburg, Cape Town, and Durban)[cite: 1, 8]. The app features an interactive city selection interface, current weather details, a 24-hour horizontal forecast, a 5-day daily forecast, and a Sun & Moon astronomical section[cite: 2, 3]. The application uses hardcoded mock data to simulate real-world weather metrics without requesting external API data[cite: 1].

 2. Development Environment
The application was debugged, tested, and verified using the following development environment[cite: 7]:
Expo: Expo SDK environment for React Native app execution[cite: 7].
React Native: Core framework for cross-platform UI components[cite: 7].
TypeScript: Type-safe JavaScript superset used for component and data structures (`.tsx`)[cite: 4, 7].
Institutional VM: Virtual machine environment used for hosting development tools[cite: 7].
BlueStacks 5: Android emulator platform running the Expo Go client[cite: 7].
Expo Go: Mobile client application used to execute and test the app on the emulator[cite: 7].

3. Error Log

| Location | Problem | Error Type | Correction |
|---|---|---|---|---|
| 1 | `App.tsx` imports | `ImageBackground` component was used in JSX but missing from the `'react-native'` import declaration[cite: 4, 8]. | Missing Import / Syntax Error | Added `ImageBackground` to the imported items from `'react-native'`[cite: 4, 8]. |
| 2 | `citySelector` component | Selecting a city compared `selectedCity` against `weather.country` instead of `weather.city`[cite: 2, 8]. | State / Logic Error | Updated the condition to `selectedCity === weather.city` and fixed `onPress` handler to pass `weather.city`[cite: 2, 8]. |
| 3 | `ImageBackground` component | The `source` prop received a raw string URL (`selectedWeather.backgroundImage`) instead of an image source object[cite: 4, 8]. | Component Property Error | Fixed the prop format to `source={{ uri: selectedWeather.backgroundImage }}`[cite: 4, 8]. |
| 4 | Current Weather section | The humidity field displayed `selectedWeather.feelsLike%` instead of humidity percentage[cite: 3, 8]. | Data Selection Error | Updated data binding to `selectedWeather.humidity%`[cite: 3, 8]. |
| 5 | 24-Hour Forecast `ScrollView` | `horizontal` prop was set to `false`, preventing horizontal scrolling of forecast items[cite: 2, 8]. | Component Property / Layout | Changed the prop to `horizontal={true}`[cite: 2, 8].
