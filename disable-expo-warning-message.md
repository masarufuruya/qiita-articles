# React Native (Expo) で黄色いワーニングを非表示にしたい (v0.63以降)

## console.disableYellowBox = trueは非推奨になった

TypeScriptを使っていると、`Use LogBox.ignoreAllLogs(disable) instead`と怒られます。

## v0.63からLogBoxがデフォルトで導入

公式サイトをみるとデバッグ機能が強化されたLogBoxが導入されたようです。

Announcing React Native 0.63 with LogBox · React Native https://reactnative.dev/blog/2020/07/06/version-0.63

## LogBox.ignoreAllLogs()を代わりに使う

```App.tsx
import { LogBox } from 'react-native';

LogBox.ignoreAllLogs()
```

これで怒られずにワーニングがでるようになります。
開発中は鬱陶しい時も多いので上手く使いましょう。
