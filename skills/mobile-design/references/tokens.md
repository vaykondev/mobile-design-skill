# Token templates

Write the tokens first, in the target's idiom. Names stay the same on every platform so screens
read the same. Values below are the Mono character; replace them with your character's values.

## SwiftUI

```swift
import SwiftUI

extension Color {
    init(hex: UInt32, opacity: Double = 1) {
        self.init(.sRGB,
                  red: Double((hex >> 16) & 0xFF) / 255,
                  green: Double((hex >> 8) & 0xFF) / 255,
                  blue: Double(hex & 0xFF) / 255,
                  opacity: opacity)
    }
}

enum AppColor {
    static let background = Color.black
    static let surface = Color(hex: 0x141414)
    static let raised = Color(hex: 0x1F1F1F)
    static let line = Color(hex: 0x2B2B2B)
    static let track = Color(hex: 0x3D3D3D)
    static let text = Color.white
    static let textSecondary = Color(hex: 0xA3A3A3)
    static let textTertiary = Color(hex: 0x808080)
    static let disabled = Color(hex: 0x4D4D4D)
    static let accent = Color.white
    static let onAccent = Color.black
    static let accentPressed = Color(hex: 0xD6D6D6)
    static let destructive = Color(hex: 0xFF453A)
    static let scrim = Color.black.opacity(0.6)
}

enum AppFont {
    static let display: Font = .largeTitle.weight(.bold).width(.expanded)   // 34, screen titles
    static let title: Font = .title2.weight(.semibold).width(.expanded)     // 22, sheet titles
    static let headline: Font = .headline                                    // 17 semibold
    static let body: Font = .body                                            // 17, rows
    static let callout: Font = .subheadline                                  // 15, tabs, labels
    static let footnote: Font = .footnote                                    // 13, explanations
    static let caption: Font = .caption                                      // 12, metadata
    static let badge: Font = .caption2.weight(.bold)                         // 11, PRO, LOG
    static let value: Font = .footnote.weight(.semibold).monospacedDigit()   // changing numbers
    static let button: Font = .body.weight(.semibold).width(.expanded)       // primary buttons
}

enum AppSpacing {
    static let xs: CGFloat = 4, sm: CGFloat = 8, md: CGFloat = 12, lg: CGFloat = 16
    static let screen: CGFloat = 20, group: CGFloat = 24, section: CGFloat = 32, giant: CGFloat = 48
    static let tapTarget: CGFloat = 44
}

enum AppRadius {
    static let media: CGFloat = 0
    static let control: CGFloat = 2
    static let sheet: CGFloat = 6
}
```

Force the theme with `.preferredColorScheme(.dark)` on the root when the character has one theme.

## React Native

```ts
export const color = {
  background: '#000000', surface: '#141414', raised: '#1F1F1F', line: '#2B2B2B', track: '#3D3D3D',
  text: '#FFFFFF', textSecondary: '#A3A3A3', textTertiary: '#808080', disabled: '#4D4D4D',
  accent: '#FFFFFF', onAccent: '#000000', accentPressed: '#D6D6D6', destructive: '#FF453A',
  scrim: 'rgba(0,0,0,0.6)',
} as const;

export const space = { xs: 4, sm: 8, md: 12, lg: 16, screen: 20, group: 24, section: 32, giant: 48, tap: 44 } as const;
export const radius = { media: 0, control: 2, sheet: 6 } as const;

// iOS: SF Pro has no "expanded" in RN — use weight 700 and letterSpacing 0.2 for titles and buttons.
export const type = {
  display: { fontSize: 34, lineHeight: 40, fontWeight: '700' },
  title: { fontSize: 22, lineHeight: 28, fontWeight: '600' },
  body: { fontSize: 17, lineHeight: 22 },
  callout: { fontSize: 15, lineHeight: 20 },
  footnote: { fontSize: 13, lineHeight: 18 },
  caption: { fontSize: 12, lineHeight: 16 },
  badge: { fontSize: 11, lineHeight: 13, fontWeight: '700' },
  value: { fontSize: 13, fontWeight: '600', fontVariant: ['tabular-nums'] },
  button: { fontSize: 17, fontWeight: '600' },
} as const;
```

## Flutter

```dart
abstract final class AppColor {
  static const background = Color(0xFF000000);
  static const surface = Color(0xFF141414);
  static const raised = Color(0xFF1F1F1F);
  static const line = Color(0xFF2B2B2B);
  static const track = Color(0xFF3D3D3D);
  static const text = Color(0xFFFFFFFF);
  static const textSecondary = Color(0xFFA3A3A3);
  static const textTertiary = Color(0xFF808080);
  static const disabled = Color(0xFF4D4D4D);
  static const accent = Color(0xFFFFFFFF);
  static const onAccent = Color(0xFF000000);
  static const destructive = Color(0xFFFF453A);
}

abstract final class AppRadius {
  static const media = 0.0, control = 2.0, sheet = 6.0;
}
```

Set `ThemeData(useMaterial3: true, scaffoldBackgroundColor: AppColor.background)` and override
`FilledButton`, `Chip`, `SegmentedButton` shapes to `RoundedRectangleBorder(borderRadius: BorderRadius.circular(AppRadius.control))`:
Material 3 defaults are pills.

## Jetpack Compose

Same values in `object AppColor { val Background = Color(0xFF000000) ... }`, shapes
`RoundedCornerShape(2.dp)` for controls and `RoundedCornerShape(topStart = 6.dp, topEnd = 6.dp)` for
sheets. Override Material 3 defaults the same way as Flutter.

## HTML mockup

```css
:root{
  --bg:#000;--surface:#141414;--raised:#1F1F1F;--line:#2B2B2B;--track:#3D3D3D;
  --text:#fff;--text-2:#A3A3A3;--text-3:#808080;--disabled:#4D4D4D;
  --accent:#fff;--on-accent:#000;--danger:#FF453A;
  --r-media:0;--r-control:2px;--r-sheet:6px;
  --font:-apple-system,'SF Pro Text',system-ui,sans-serif;
}
.title{font:700 34px/40px var(--font);font-stretch:expanded}
.btn{height:52px;border-radius:var(--r-control);background:var(--accent);color:var(--on-accent);
     font:600 17px var(--font);font-stretch:expanded}
.num{font-variant-numeric:tabular-nums}
```

Frame each screen at 402 × 874 with a 54 pt status bar and a 5 pt home indicator 8 pt from the bottom.

## Shared components to build on the tokens

- **Primary button:** accent fill, onAccent text, 52 tall, radius control, full width minus 2 × screen margin.
- **Secondary button:** no fill, 1 pt `track` border, text colour.
- **Text button:** text only, `textSecondary`, 44 tall hit area.
- **Chip:** 32 tall, 12 horizontal padding, radius control; selected = accent fill, unselected = 1 pt `line` border.
- **Segmented control:** equal segments in a 1 pt `line` frame; selected segment = accent fill.
- **Toggle:** a square one (radius control) reads as part of the system; the platform toggle is fine for a light character.
- **Row:** 48 to 56 tall, title left in body, value right in `textSecondary` + chevron, `line` separator under.
- **Section label:** footnote, `textSecondary`, 24 above the group, 8 below.
- **Badge:** badge font, 2 × 6 padding, radius control, white on black or black on white.
