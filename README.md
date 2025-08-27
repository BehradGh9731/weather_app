# Weather App (Flutter + BLoC)

Say hello to your friendly neighborhood weather app! ☀️🌧️ Built **only with Dart & Flutter**, it shows clean, useful weather info with a **nice & friendly UI** and a tidy **BLoC** architecture — perfect for learning and for daily use.

> Repository: `https://github.com/BehradGh9731/weather_app.git`

---

## 📸 Preview
![image alt](https://github.com/BehradGh9731/weather_app/blob/3ee5d68fa9c977f348bebe64451285981143e047/1.jpg)


---

## ✨ Highlights

* **Clean 1‑screen experience** with responsive, friendly visuals
* **BLoC state management** for predictable UI updates
* Clear folder structure, easy to extend
* Pure Flutter widgets — **no non‑Flutter build tools**

---

## 🧱 Project Structure (exactly as in repo)

```
weather_app/
├─ .dart_tool/
├─ .idea/
├─ android/
├─ assets/
├─ build/
├─ ios/
├─ lib/
│  ├─ data/                      
│  ├─ bloc/
│  │  ├─ weather_bloc_bloc.dart
│  │  ├─ weather_bloc_event.dart
│  │  └─ weather_bloc_state.dart
│  ├─ my_data.dart               # (e.g., API base URL / key constants)
│  ├─ screens/
│  │  └─ home_screen.dart
│  └─ main.dart
├─ linux/
├─ macos/
├─ test/
├─ web/
├─ windows/
└─ README.md
```

> `my_data.dart` is a convenient place for constants like API endpoints or keys (if used in your implementation).

---

## 🔧 Requirements

* **Flutter SDK** 3.x or newer (includes Dart SDK)
* A configured device or emulator:

  * Android emulator / physical device with USB debugging
  * iOS Simulator / physical device (macOS + Xcode required)
  * Or Flutter Web via Chrome (optional)

Verify your setup:

```bash
flutter --version
flutter doctor
```

---

## 🚀 Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/BehradGh9731/weather_app.git
   cd weather_app
   ```
2. **Install dependencies**

   ```bash
   flutter pub get
   ```
3. **(Optional) Configure constants**

   * Open `lib/my_data.dart` and set any required constants (e.g., API base URL or key) according to your code.

---

## ▶️ Run the Program (Dart & Flutter only)

> Run directly with the **Flutter CLI** — no extra build tools.

* **Run on the current device**

  ```bash
  flutter run
  ```

* **Choose a specific device**

  ```bash
  flutter devices
  flutter run -d <device_id>
  ```

* **Run on Web (optional, if enabled)**

  ```bash
  flutter run -d chrome
  ```

> If no devices appear, start an emulator from Android Studio/VS Code or connect a physical device.

---

## 🧭 Architecture (BLoC quick view)

* `weather_bloc_event.dart` — incoming intents (e.g., fetch weather)
* `weather_bloc_state.dart` — UI states (loading, loaded, error)
* `weather_bloc_bloc.dart` — maps events ➜ states (business logic)
* `home_screen.dart` — renders UI based on `BlocBuilder` state

Concept snippet:

```dart
BlocBuilder<WeatherBloc, WeatherState>(
  builder: (context, state) {
    if (state is WeatherLoading) return const CircularProgressIndicator();
    if (state is WeatherLoaded)  return WeatherView(data: state.data);
    if (state is WeatherError)   return Text(state.message);
    return const SizedBox.shrink();
  },
);
```

---

## 🖌️ UI Notes

* Friendly typography and spacing for quick scanning
* Simple color palette suitable for light/dark modes
* Adaptive layout that feels good on phone and small tablets

---

## 📦 Build (Flutter CLI)

* **Android (APK, release)**

  ```bash
  flutter build apk --release
  ```
* **iOS (release)**

  ```bash
  flutter build ios --release
  ```
* **Web (release)**

  ```bash
  flutter build web --release
  ```

> iOS release builds require macOS and Xcode — still Flutter‑only commands.

---

## 🐞 Troubleshooting

* **No devices found** → `flutter devices`, start an emulator or connect a device
* **Network/API issues** → Verify values in `lib/my_data.dart`, check connectivity
* **Build hiccups** → `flutter clean && flutter pub get`, then `flutter doctor`

---

## 🤝 Contributing

Issues and PRs are welcome. If proposing new features (e.g., hourly forecast, theming), please open an issue to discuss first.

---

## 📄 License

Add your preferred license (e.g., MIT) in `LICENSE`.
