![Package art](./docs/header.png)

[![codecov](https://codecov.io/gh/mark-nicepants/figma2flutter/branch/main/graph/badge.svg?token=CEO88366WO)](https://codecov.io/gh/mark-nicepants/figma2flutter)
[![pub package](https://img.shields.io/pub/v/figma2flutter.svg)](https://pub.dev/packages/figma2flutter)

This package converts [Tokens Studio for Figma](https://docs.tokens.studio/) json exports into Flutter code.

**[Notice] You may use this package but breaking changes may occur when relying on releases lower than v1.0.0**

## How to use

### 1. Install

```
dart pub global activate figma2flutter
```

### 2. Export 

Export your tokens from Figma and save the json file in your project folder.

You can do this manually or use the [Tokens Studio for Figma](https://docs.tokens.studio/) plugin to export your tokens directly into your repository.

### 3. Generate
Run the command in the root of your project
```
figma2flutter --input <path_to_json_file> --output <path_to_output_folder>
```

Default config values are:
  
```
--input: ./design/tokens.json
--output: ./lib/assets/tokens/
```

## Token support (checked = supported)

[Overview of all tokens available here](https://docs.tokens.studio/available-tokens/available-tokens)

- [sizing](https://docs.tokens.studio/available-tokens/sizing-tokens)
- ✅ [spacing](https://docs.tokens.studio/available-tokens/spacing-tokens) (output = EdgeInsets)
  - ✅ 1, 2, 3 or 4 values
  - ✅ accept int/double values, px of rem suffix
- [color](https://docs.tokens.studio/available-tokens/color-tokens)
  - ✅ Solid (output = Color)
    - ✅ hex
    - ✅ rgb 
    - ✅ rgba
    - ✅ hsla
  - Gradients
- [borderRadius](https://docs.tokens.studio/available-tokens/border-radius-tokens)
- [borderWidth](https://docs.tokens.studio/available-tokens/border-width-tokens)
- [boxShadow](https://docs.tokens.studio/available-tokens/shadow-tokens)
- [opacity](https://docs.tokens.studio/available-tokens/opacity-tokens)
- ✅ [typography](https://docs.tokens.studio/available-tokens/typography-tokens) (output = TextStyle)
  - ✅ fontFamilies
  - ✅ fontWeights
  - ✅ fontSizes
  - ✅ lineHeight
  - letterSpacing
  - paragraphSpacing
  - textCase
  - textDecoration
- [asset](https://docs.tokens.studio/available-tokens/asset-tokens)
- [composition (pro)](https://docs.tokens.studio/available-tokens/composition-tokens)
- [dimension](https://docs.tokens.studio/available-tokens/dimension-tokens)
- [border](https://docs.tokens.studio/available-tokens/border-tokens)

## Ideas for contributing

- Add an example that illustrates how to use the package
- Generate a view similar to the Figma plugin (sort of a tokens Gallery)
- Generate MaterialColors when we have multiple color values and int base keys (100, 200, 300, 400)
- Generate extensions for Gap to easily allow spacing tokens to be used as Gap (spacing.small=4 => Gap.small => const Gap(4))